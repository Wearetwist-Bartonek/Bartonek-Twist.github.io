<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Protokoly – Předávací a montážní listy</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        :root {
            --primary: #0d9488; --primary-dark: #0f766e; --primary-light: #ccfbf1;
            --success: #10b981; --success-light: #d1fae5;
            --danger: #ef4444; --danger-light: #fee2e2;
            --warning: #f59e0b; --warning-light: #fef3c7;
            --blue: #3b82f6; --blue-light: #dbeafe;
            --purple: #8b5cf6; --purple-light: #ede9fe;
            --gray: #6b7280; --gray-light: #f3f4f6;
            --bg: #ffffff; --bg-secondary: #f0fdfa; --bg-dark: #134e4a;
            --border: #e5e7eb; --text: #111827; --text-muted: #6b7280;
            --radius: 12px;
        }
        body { font-family: system-ui, -apple-system, sans-serif; background: var(--bg-secondary); color: var(--text); line-height: 1.5; }
        
        .app-container { display: grid; grid-template-columns: 320px 1fr; min-height: 100vh; }
        @media (max-width: 1024px) { .app-container { grid-template-columns: 1fr; } }
        
        /* Sidebar */
        .sidebar { background: var(--bg); border-right: 1px solid var(--border); display: flex; flex-direction: column; }
        .sidebar-header { 
            background: linear-gradient(135deg, var(--bg-dark) 0%, #115e59 100%);
            color: white; 
            padding: 1.5rem;
        }
        .sidebar-header h1 { font-size: 1.25rem; font-weight: 700; display: flex; align-items: center; gap: 0.5rem; }
        .sidebar-header p { font-size: 0.8rem; opacity: 0.8; margin-top: 0.25rem; }
        
        .sidebar-actions { padding: 1rem; border-bottom: 1px solid var(--border); }
        .sidebar-actions .btn { width: 100%; justify-content: center; }
        
        .protocol-list { flex: 1; overflow-y: auto; padding: 0.5rem; }
        .protocol-item { 
            padding: 1rem;
            border: 1px solid var(--border);
            border-radius: 8px;
            margin-bottom: 0.5rem;
            cursor: pointer;
            transition: all 0.15s;
        }
        .protocol-item:hover { border-color: var(--primary); }
        .protocol-item.active { border-color: var(--primary); background: var(--primary-light); }
        .protocol-item-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 0.5rem; }
        .protocol-item-number { font-weight: 600; font-size: 0.9rem; }
        .protocol-item-type { font-size: 0.65rem; padding: 0.15rem 0.5rem; border-radius: 4px; font-weight: 600; text-transform: uppercase; }
        .type-handover { background: var(--blue-light); color: var(--blue); }
        .type-installation { background: var(--success-light); color: #047857; }
        .type-service { background: var(--warning-light); color: #b45309; }
        .type-return { background: var(--purple-light); color: var(--purple); }
        .protocol-item-title { font-size: 0.85rem; color: var(--text); margin-bottom: 0.25rem; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
        .protocol-item-meta { font-size: 0.75rem; color: var(--text-muted); }
        
        .sidebar-footer { padding: 1rem; border-top: 1px solid var(--border); }
        
        /* Main Content */
        .main-content { display: flex; flex-direction: column; overflow: hidden; }
        .main-header { 
            background: var(--bg); 
            padding: 1rem 1.5rem; 
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }
        .main-title { font-size: 1.1rem; font-weight: 600; }
        .main-actions { display: flex; gap: 0.5rem; }
        
        /* Buttons */
        .btn { 
            padding: 0.5rem 1rem; 
            border: none; 
            border-radius: 8px; 
            font-size: 0.8rem; 
            font-weight: 600; 
            cursor: pointer; 
            transition: all 0.15s;
            display: inline-flex;
            align-items: center;
            gap: 0.4rem;
            font-family: inherit;
        }
        .btn-primary { background: var(--primary); color: white; }
        .btn-primary:hover { background: var(--primary-dark); }
        .btn-success { background: var(--success); color: white; }
        .btn-danger { background: var(--danger); color: white; }
        .btn-outline { background: white; color: var(--text); border: 1px solid var(--border); }
        .btn-outline:hover { border-color: var(--primary); color: var(--primary); }
        .btn-sm { padding: 0.35rem 0.75rem; font-size: 0.75rem; }
        
        /* Editor */
        .editor { flex: 1; overflow-y: auto; padding: 1.5rem; }
        .editor-section { background: var(--bg); border: 1px solid var(--border); border-radius: var(--radius); margin-bottom: 1rem; }
        .editor-section-header { 
            padding: 0.75rem 1rem; 
            border-bottom: 1px solid var(--border); 
            font-weight: 600; 
            font-size: 0.85rem;
            background: var(--bg-secondary);
            border-radius: var(--radius) var(--radius) 0 0;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .editor-section-body { padding: 1rem; }
        
        /* Form */
        .form-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1rem; }
        .form-grid.cols-3 { grid-template-columns: repeat(3, 1fr); }
        .form-group { display: flex; flex-direction: column; gap: 0.25rem; }
        .form-group.full { grid-column: 1 / -1; }
        .form-group label { font-size: 0.7rem; font-weight: 600; color: var(--text-muted); text-transform: uppercase; }
        .form-group input, .form-group select, .form-group textarea { 
            padding: 0.55rem 0.75rem; 
            border: 1px solid var(--border); 
            border-radius: 6px; 
            font-size: 0.85rem;
            font-family: inherit;
        }
        .form-group input:focus, .form-group select:focus, .form-group textarea:focus { 
            outline: none; 
            border-color: var(--primary); 
            box-shadow: 0 0 0 3px var(--primary-light); 
        }
        .form-group textarea { min-height: 80px; resize: vertical; }
        
        /* Items Table */
        .items-table { width: 100%; border-collapse: collapse; font-size: 0.85rem; }
        .items-table th { 
            background: var(--bg-secondary); 
            padding: 0.6rem; 
            text-align: left; 
            font-weight: 600; 
            font-size: 0.7rem;
            text-transform: uppercase;
            color: var(--text-muted);
            border-bottom: 2px solid var(--border);
        }
        .items-table td { padding: 0.5rem; border-bottom: 1px solid var(--border); vertical-align: middle; }
        .items-table input, .items-table select { 
            width: 100%; 
            padding: 0.4rem; 
            border: 1px solid var(--border); 
            border-radius: 4px; 
            font-size: 0.8rem;
        }
        .items-table .btn-remove { 
            background: none; 
            border: none; 
            color: var(--danger); 
            cursor: pointer; 
            font-size: 1.1rem;
            opacity: 0.5;
            padding: 0;
        }
        .items-table .btn-remove:hover { opacity: 1; }
        
        /* Signature */
        .signature-area { 
            border: 2px dashed var(--border); 
            border-radius: 8px; 
            padding: 1rem;
            text-align: center;
            min-height: 100px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.15s;
        }
        .signature-area:hover { border-color: var(--primary); background: var(--primary-light); }
        .signature-area.has-signature { border-style: solid; cursor: default; }
        .signature-area.has-signature:hover { background: transparent; }
        .signature-canvas { border: 1px solid var(--border); border-radius: 4px; background: white; cursor: crosshair; }
        .signature-preview { max-width: 100%; max-height: 80px; }
        
        /* Checklist */
        .checklist-item { 
            display: flex; 
            align-items: center; 
            gap: 0.75rem; 
            padding: 0.6rem;
            border-bottom: 1px solid var(--border);
        }
        .checklist-item:last-child { border-bottom: none; }
        .checklist-item input[type="checkbox"] { width: 18px; height: 18px; cursor: pointer; }
        .checklist-item label { flex: 1; font-size: 0.85rem; cursor: pointer; }
        .checklist-item select { width: 120px; padding: 0.3rem; font-size: 0.8rem; border: 1px solid var(--border); border-radius: 4px; }
        
        /* Status badge */
        .status-badge { 
            display: inline-flex;
            align-items: center;
            gap: 0.35rem;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
        }
        .status-draft { background: var(--gray-light); color: var(--gray); }
        .status-completed { background: var(--success-light); color: #047857; }
        .status-signed { background: var(--primary-light); color: var(--primary-dark); }
        
        /* Empty State */
        .empty-state { 
            text-align: center; 
            padding: 4rem 2rem;
            color: var(--text-muted);
        }
        .empty-icon { font-size: 4rem; margin-bottom: 1rem; opacity: 0.5; }
        .empty-title { font-size: 1.1rem; font-weight: 600; color: var(--text); margin-bottom: 0.5rem; }
        
        /* Modal */
        .modal-overlay { 
            position: fixed; 
            inset: 0; 
            background: rgba(0,0,0,0.5); 
            display: flex; 
            align-items: center; 
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.2s;
            padding: 1rem;
        }
        .modal-overlay.active { opacity: 1; visibility: visible; }
        .modal { 
            background: var(--bg); 
            border-radius: var(--radius); 
            width: 100%;
            max-width: 500px;
            transform: translateY(20px);
            transition: transform 0.2s;
        }
        .modal-overlay.active .modal { transform: translateY(0); }
        .modal-header { 
            padding: 1.25rem 1.5rem; 
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .modal-title { font-weight: 700; font-size: 1.1rem; }
        .modal-close { background: none; border: none; font-size: 1.5rem; cursor: pointer; color: var(--text-muted); }
        .modal-body { padding: 1.5rem; }
        .modal-footer { padding: 1rem 1.5rem; border-top: 1px solid var(--border); display: flex; justify-content: flex-end; gap: 0.5rem; }
        
        /* Toast */
        .toast { 
            position: fixed; 
            bottom: 2rem; 
            right: 2rem; 
            background: var(--bg-dark); 
            color: white; 
            padding: 1rem 1.5rem; 
            border-radius: 8px;
            font-size: 0.875rem;
            box-shadow: 0 4px 20px rgba(0,0,0,0.3);
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s;
            z-index: 1001;
        }
        .toast.show { transform: translateY(0); opacity: 1; }
        .toast.success { background: var(--success); }
        
        /* Print Preview */
        .print-preview { 
            background: white; 
            width: 210mm; 
            min-height: 297mm;
            padding: 15mm;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            margin: 0 auto;
            font-size: 10pt;
        }
        
        .print-header { 
            display: flex; 
            justify-content: space-between; 
            align-items: flex-start;
            margin-bottom: 8mm;
            padding-bottom: 5mm;
            border-bottom: 2px solid var(--primary);
        }
        .print-title { font-size: 18pt; font-weight: 700; color: var(--primary); }
        .print-number { font-size: 10pt; color: var(--text-muted); margin-top: 1mm; }
        .print-type-badge { 
            padding: 2mm 4mm; 
            border-radius: 4px; 
            font-size: 8pt; 
            font-weight: 600;
            text-transform: uppercase;
        }
        
        .print-parties { display: grid; grid-template-columns: 1fr 1fr; gap: 8mm; margin-bottom: 8mm; }
        .print-party { padding: 4mm; border-radius: 2mm; }
        .print-party.supplier { background: #f0fdfa; }
        .print-party.customer { background: #fef3c7; }
        .print-party-label { font-size: 7pt; font-weight: 700; text-transform: uppercase; color: var(--text-muted); margin-bottom: 2mm; }
        .print-party-name { font-size: 11pt; font-weight: 700; margin-bottom: 1mm; }
        .print-party-details { font-size: 8pt; color: #374151; }
        
        .print-meta { display: grid; grid-template-columns: repeat(4, 1fr); gap: 4mm; margin-bottom: 8mm; padding: 4mm; background: #f8fafc; border-radius: 2mm; }
        .print-meta-item label { display: block; font-size: 6pt; font-weight: 600; text-transform: uppercase; color: var(--text-muted); margin-bottom: 1mm; }
        .print-meta-item span { font-size: 9pt; font-weight: 600; }
        
        .print-section { margin-bottom: 6mm; }
        .print-section-title { font-size: 9pt; font-weight: 700; color: var(--primary); margin-bottom: 3mm; padding-bottom: 1mm; border-bottom: 1px solid var(--border); }
        
        .print-table { width: 100%; border-collapse: collapse; font-size: 8pt; }
        .print-table th { background: var(--bg-dark); color: white; padding: 2mm; text-align: left; font-size: 7pt; }
        .print-table td { padding: 2mm; border-bottom: 1px solid var(--border); }
        
        .print-checklist { }
        .print-checklist-item { display: flex; align-items: center; gap: 3mm; padding: 2mm 0; border-bottom: 1px solid var(--border); font-size: 8pt; }
        .print-checklist-item:last-child { border-bottom: none; }
        .print-checkbox { width: 4mm; height: 4mm; border: 1px solid var(--text); display: inline-flex; align-items: center; justify-content: center; font-size: 8pt; }
        .print-checkbox.checked { background: var(--success); border-color: var(--success); color: white; }
        
        .print-notes { font-size: 8pt; padding: 3mm; background: #f8fafc; border-radius: 2mm; white-space: pre-wrap; }
        
        .print-signatures { display: grid; grid-template-columns: 1fr 1fr; gap: 15mm; margin-top: 10mm; }
        .print-signature-box { text-align: center; }
        .print-signature-line { border-top: 1px solid var(--text); margin-top: 20mm; padding-top: 2mm; }
        .print-signature-label { font-size: 7pt; color: var(--text-muted); }
        .print-signature-name { font-size: 8pt; font-weight: 600; margin-top: 1mm; }
        .print-signature-img { max-height: 15mm; margin-bottom: 2mm; }
        
        .print-footer { margin-top: 10mm; padding-top: 5mm; border-top: 1px solid var(--border); font-size: 7pt; color: var(--text-muted); text-align: center; }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .sidebar { display: none; }
            .form-grid { grid-template-columns: 1fr; }
            .print-preview { width: 100%; min-height: auto; padding: 5mm; }
        }
        
        /* Print */
        @media print {
            body { background: white; }
            .sidebar, .main-header, .editor, .toast { display: none !important; }
            .print-preview { box-shadow: none; padding: 0; }
        }
    </style>
</head>
<body>
<div class="app-container">
    <!-- Sidebar -->
    <div class="sidebar">
        <div class="sidebar-header">
            <h1>📋 Protokoly</h1>
            <p>Předávací a montážní listy</p>
        </div>
        
        <div class="sidebar-actions">
            <button class="btn btn-primary" onclick="App.newProtocol()">+ Nový protokol</button>
        </div>
        
        <div class="protocol-list" id="protocolList"></div>
        
        <div class="sidebar-footer">
            <button class="btn btn-outline btn-sm" onclick="App.exportAll()" style="width: 100%;">📥 Exportovat vše</button>
        </div>
    </div>
    
    <!-- Main Content -->
    <div class="main-content">
        <div class="main-header">
            <div>
                <span class="main-title" id="mainTitle">Nový protokol</span>
                <span class="status-badge status-draft" id="statusBadge">Koncept</span>
            </div>
            <div class="main-actions">
                <button class="btn btn-outline" onclick="App.preview()">👁️ Náhled</button>
                <button class="btn btn-outline" onclick="App.duplicate()">📄 Duplikovat</button>
                <button class="btn btn-success" onclick="App.exportPDF()">📄 Export PDF</button>
                <button class="btn btn-danger btn-sm" onclick="App.deleteProtocol()" id="deleteBtn" style="display: none;">🗑️</button>
            </div>
        </div>
        
        <div class="editor" id="editor">
            <!-- Basic Info -->
            <div class="editor-section">
                <div class="editor-section-header">📋 Základní údaje</div>
                <div class="editor-section-body">
                    <div class="form-grid">
                        <div class="form-group">
                            <label>Typ protokolu</label>
                            <select id="protocolType" onchange="App.onTypeChange()">
                                <option value="handover">📦 Předávací protokol</option>
                                <option value="installation">🔧 Montážní list</option>
                                <option value="service">🛠️ Servisní protokol</option>
                                <option value="return">↩️ Protokol o vrácení</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Číslo protokolu</label>
                            <input type="text" id="protocolNumber" placeholder="PRO-2024-001">
                        </div>
                        <div class="form-group">
                            <label>Datum</label>
                            <input type="date" id="protocolDate">
                        </div>
                        <div class="form-group">
                            <label>Místo</label>
                            <input type="text" id="protocolPlace" placeholder="Praha">
                        </div>
                        <div class="form-group full">
                            <label>Předmět / Název zakázky</label>
                            <input type="text" id="protocolSubject" placeholder="Instalace klimatizace">
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Supplier -->
            <div class="editor-section">
                <div class="editor-section-header">🏢 Dodavatel / Předávající</div>
                <div class="editor-section-body">
                    <div class="form-grid">
                        <div class="form-group full">
                            <label>Název firmy</label>
                            <input type="text" id="supplierName" placeholder="Vaše firma s.r.o.">
                        </div>
                        <div class="form-group">
                            <label>IČO</label>
                            <input type="text" id="supplierIco" placeholder="12345678">
                        </div>
                        <div class="form-group">
                            <label>Zastoupený</label>
                            <input type="text" id="supplierPerson" placeholder="Jan Novák">
                        </div>
                        <div class="form-group full">
                            <label>Adresa</label>
                            <input type="text" id="supplierAddress" placeholder="Ulice 123, Město">
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Customer -->
            <div class="editor-section">
                <div class="editor-section-header">👤 Objednavatel / Přebírající</div>
                <div class="editor-section-body">
                    <div class="form-grid">
                        <div class="form-group full">
                            <label>Název / Jméno</label>
                            <input type="text" id="customerName" placeholder="Zákazník a.s.">
                        </div>
                        <div class="form-group">
                            <label>IČO</label>
                            <input type="text" id="customerIco" placeholder="">
                        </div>
                        <div class="form-group">
                            <label>Zastoupený</label>
                            <input type="text" id="customerPerson" placeholder="">
                        </div>
                        <div class="form-group full">
                            <label>Adresa</label>
                            <input type="text" id="customerAddress" placeholder="">
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Items -->
            <div class="editor-section">
                <div class="editor-section-header">📦 Položky / Předmět předání</div>
                <div class="editor-section-body">
                    <table class="items-table">
                        <thead>
                            <tr>
                                <th style="width: 40%;">Popis</th>
                                <th style="width: 15%;">Množství</th>
                                <th style="width: 15%;">Jednotka</th>
                                <th style="width: 15%;">Sériové č.</th>
                                <th style="width: 10%;">Stav</th>
                                <th style="width: 5%;"></th>
                            </tr>
                        </thead>
                        <tbody id="itemsBody"></tbody>
                    </table>
                    <button class="btn btn-outline btn-sm" onclick="App.addItem()" style="margin-top: 0.75rem;">+ Přidat položku</button>
                </div>
            </div>
            
            <!-- Checklist -->
            <div class="editor-section" id="checklistSection">
                <div class="editor-section-header">✅ Kontrolní seznam</div>
                <div class="editor-section-body">
                    <div id="checklistBody"></div>
                    <div style="display: flex; gap: 0.5rem; margin-top: 0.75rem;">
                        <input type="text" id="newCheckItem" placeholder="Nová položka kontroly..." style="flex: 1; padding: 0.5rem; border: 1px solid var(--border); border-radius: 6px;">
                        <button class="btn btn-outline btn-sm" onclick="App.addCheckItem()">+ Přidat</button>
                    </div>
                </div>
            </div>
            
            <!-- Notes -->
            <div class="editor-section">
                <div class="editor-section-header">📝 Poznámky a závady</div>
                <div class="editor-section-body">
                    <textarea id="protocolNotes" placeholder="Poznámky, zjištěné závady, výhrady..." style="width: 100%; min-height: 100px;"></textarea>
                </div>
            </div>
            
            <!-- Signatures -->
            <div class="editor-section">
                <div class="editor-section-header">✍️ Podpisy</div>
                <div class="editor-section-body">
                    <div class="form-grid">
                        <div class="form-group">
                            <label>Podpis předávajícího</label>
                            <div class="signature-area" id="signatureSupplier" onclick="App.openSignature('supplier')">
                                <span style="font-size: 2rem; opacity: 0.3;">✍️</span>
                                <span style="font-size: 0.8rem; color: var(--text-muted);">Klikněte pro podpis</span>
                            </div>
                        </div>
                        <div class="form-group">
                            <label>Podpis přebírajícího</label>
                            <div class="signature-area" id="signatureCustomer" onclick="App.openSignature('customer')">
                                <span style="font-size: 2rem; opacity: 0.3;">✍️</span>
                                <span style="font-size: 0.8rem; color: var(--text-muted);">Klikněte pro podpis</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Print Preview (hidden by default) -->
        <div id="printPreviewContainer" style="display: none; padding: 1.5rem; overflow-y: auto;">
            <div style="text-align: center; margin-bottom: 1rem;">
                <button class="btn btn-outline" onclick="App.closePreview()">← Zpět na editor</button>
                <button class="btn btn-success" onclick="App.exportPDF()">📄 Stáhnout PDF</button>
            </div>
            <div class="print-preview" id="printPreview"></div>
        </div>
    </div>
</div>

<!-- Signature Modal -->
<div class="modal-overlay" id="signatureModal">
    <div class="modal">
        <div class="modal-header">
            <span class="modal-title">✍️ Podpis</span>
            <button class="modal-close" onclick="App.closeSignature()">×</button>
        </div>
        <div class="modal-body" style="text-align: center;">
            <canvas id="signatureCanvas" class="signature-canvas" width="400" height="150"></canvas>
            <div style="margin-top: 0.75rem;">
                <button class="btn btn-outline btn-sm" onclick="App.clearSignature()">🗑️ Vymazat</button>
            </div>
        </div>
        <div class="modal-footer">
            <button class="btn btn-outline" onclick="App.closeSignature()">Zrušit</button>
            <button class="btn btn-primary" onclick="App.saveSignature()">💾 Uložit podpis</button>
        </div>
    </div>
</div>

<!-- Toast -->
<div class="toast" id="toast"></div>

<script>
const App = {
    protocols: [],
    currentId: null,
    items: [],
    checklist: [],
    signatures: { supplier: null, customer: null },
    signatureTarget: null,
    isDrawing: false,
    counter: 0,
    
    defaultChecklists: {
        handover: ['Kompletnost dodávky', 'Stav balení', 'Funkčnost', 'Dokumentace přiložena'],
        installation: ['Příprava pracoviště', 'Montáž provedena', 'Funkční zkouška', 'Úklid pracoviště', 'Zaškolení obsluhy'],
        service: ['Diagnostika', 'Oprava provedena', 'Testování', 'Výměna dílů'],
        return: ['Kompletnost', 'Stav produktu', 'Příslušenství', 'Poškození']
    },
    
    typeLabels: {
        handover: { name: 'Předávací protokol', class: 'type-handover' },
        installation: { name: 'Montážní list', class: 'type-installation' },
        service: { name: 'Servisní protokol', class: 'type-service' },
        return: { name: 'Protokol o vrácení', class: 'type-return' }
    },
    
    init() {
        this.loadData();
        this.loadSupplier();
        this.renderList();
        if (this.protocols.length > 0) {
            this.loadProtocol(this.protocols[0].id);
        } else {
            this.newProtocol();
        }
        this.initSignatureCanvas();
    },
    
    // Data
    loadData() {
        try {
            const data = localStorage.getItem('protocols_data');
            if (data) this.protocols = JSON.parse(data);
            const counter = localStorage.getItem('protocols_counter');
            if (counter) this.counter = parseInt(counter);
        } catch (e) { console.error(e); }
    },
    
    saveData() {
        localStorage.setItem('protocols_data', JSON.stringify(this.protocols));
        localStorage.setItem('protocols_counter', this.counter);
    },
    
    loadSupplier() {
        try {
            const supplier = localStorage.getItem('protocols_supplier');
            if (supplier) {
                const s = JSON.parse(supplier);
                document.getElementById('supplierName').value = s.name || '';
                document.getElementById('supplierIco').value = s.ico || '';
                document.getElementById('supplierAddress').value = s.address || '';
            }
        } catch (e) {}
    },
    
    saveSupplier() {
        const supplier = {
            name: document.getElementById('supplierName').value,
            ico: document.getElementById('supplierIco').value,
            address: document.getElementById('supplierAddress').value
        };
        localStorage.setItem('protocols_supplier', JSON.stringify(supplier));
    },
    
    // Protocol management
    newProtocol() {
        this.currentId = null;
        this.items = [{ id: Date.now(), description: '', quantity: 1, unit: 'ks', serial: '', condition: 'ok' }];
        this.checklist = this.defaultChecklists.handover.map((text, i) => ({ id: i, text, checked: false, note: '' }));
        this.signatures = { supplier: null, customer: null };
        
        document.getElementById('protocolType').value = 'handover';
        document.getElementById('protocolNumber').value = this.generateNumber();
        document.getElementById('protocolDate').value = new Date().toISOString().split('T')[0];
        document.getElementById('protocolPlace').value = '';
        document.getElementById('protocolSubject').value = '';
        document.getElementById('supplierPerson').value = '';
        document.getElementById('customerName').value = '';
        document.getElementById('customerIco').value = '';
        document.getElementById('customerPerson').value = '';
        document.getElementById('customerAddress').value = '';
        document.getElementById('protocolNotes').value = '';
        
        this.loadSupplier();
        this.renderItems();
        this.renderChecklist();
        this.renderSignatures();
        this.updateUI();
        document.getElementById('deleteBtn').style.display = 'none';
    },
    
    generateNumber() {
        this.counter++;
        const year = new Date().getFullYear();
        return `PRO-${year}-${String(this.counter).padStart(3, '0')}`;
    },
    
    loadProtocol(id) {
        const protocol = this.protocols.find(p => p.id === id);
        if (!protocol) return;
        
        this.currentId = id;
        this.items = [...(protocol.items || [])];
        this.checklist = [...(protocol.checklist || [])];
        this.signatures = { ...(protocol.signatures || { supplier: null, customer: null }) };
        
        document.getElementById('protocolType').value = protocol.type || 'handover';
        document.getElementById('protocolNumber').value = protocol.number || '';
        document.getElementById('protocolDate').value = protocol.date || '';
        document.getElementById('protocolPlace').value = protocol.place || '';
        document.getElementById('protocolSubject').value = protocol.subject || '';
        document.getElementById('supplierName').value = protocol.supplier?.name || '';
        document.getElementById('supplierIco').value = protocol.supplier?.ico || '';
        document.getElementById('supplierPerson').value = protocol.supplier?.person || '';
        document.getElementById('supplierAddress').value = protocol.supplier?.address || '';
        document.getElementById('customerName').value = protocol.customer?.name || '';
        document.getElementById('customerIco').value = protocol.customer?.ico || '';
        document.getElementById('customerPerson').value = protocol.customer?.person || '';
        document.getElementById('customerAddress').value = protocol.customer?.address || '';
        document.getElementById('protocolNotes').value = protocol.notes || '';
        
        this.renderItems();
        this.renderChecklist();
        this.renderSignatures();
        this.updateUI();
        this.renderList();
        document.getElementById('deleteBtn').style.display = '';
    },
    
    saveProtocol() {
        const data = this.collectData();
        
        if (this.currentId) {
            const idx = this.protocols.findIndex(p => p.id === this.currentId);
            if (idx !== -1) {
                data.id = this.currentId;
                data.createdAt = this.protocols[idx].createdAt;
                this.protocols[idx] = data;
            }
        } else {
            data.id = Date.now().toString(36) + Math.random().toString(36).substr(2);
            data.createdAt = new Date().toISOString();
            this.currentId = data.id;
            this.protocols.unshift(data);
        }
        
        this.saveSupplier();
        this.saveData();
        this.renderList();
        this.updateUI();
        document.getElementById('deleteBtn').style.display = '';
        this.showToast('Protokol uložen', 'success');
    },
    
    collectData() {
        return {
            type: document.getElementById('protocolType').value,
            number: document.getElementById('protocolNumber').value,
            date: document.getElementById('protocolDate').value,
            place: document.getElementById('protocolPlace').value,
            subject: document.getElementById('protocolSubject').value,
            supplier: {
                name: document.getElementById('supplierName').value,
                ico: document.getElementById('supplierIco').value,
                person: document.getElementById('supplierPerson').value,
                address: document.getElementById('supplierAddress').value
            },
            customer: {
                name: document.getElementById('customerName').value,
                ico: document.getElementById('customerIco').value,
                person: document.getElementById('customerPerson').value,
                address: document.getElementById('customerAddress').value
            },
            items: this.items,
            checklist: this.checklist,
            notes: document.getElementById('protocolNotes').value,
            signatures: this.signatures,
            updatedAt: new Date().toISOString()
        };
    },
    
    deleteProtocol() {
        if (!this.currentId || !confirm('Smazat tento protokol?')) return;
        this.protocols = this.protocols.filter(p => p.id !== this.currentId);
        this.saveData();
        this.renderList();
        if (this.protocols.length > 0) {
            this.loadProtocol(this.protocols[0].id);
        } else {
            this.newProtocol();
        }
        this.showToast('Protokol smazán', 'success');
    },
    
    duplicate() {
        this.saveProtocol();
        this.currentId = null;
        document.getElementById('protocolNumber').value = this.generateNumber();
        this.signatures = { supplier: null, customer: null };
        this.renderSignatures();
        this.saveProtocol();
    },
    
    // UI
    updateUI() {
        const type = document.getElementById('protocolType').value;
        const typeInfo = this.typeLabels[type];
        document.getElementById('mainTitle').textContent = document.getElementById('protocolNumber').value || 'Nový protokol';
        
        const hasSig = this.signatures.supplier || this.signatures.customer;
        const badge = document.getElementById('statusBadge');
        if (hasSig) {
            badge.className = 'status-badge status-signed';
            badge.textContent = '✅ Podepsáno';
        } else if (this.currentId) {
            badge.className = 'status-badge status-completed';
            badge.textContent = '📋 Uloženo';
        } else {
            badge.className = 'status-badge status-draft';
            badge.textContent = 'Koncept';
        }
    },
    
    onTypeChange() {
        const type = document.getElementById('protocolType').value;
        this.checklist = this.defaultChecklists[type].map((text, i) => ({ id: i, text, checked: false, note: '' }));
        this.renderChecklist();
    },
    
    renderList() {
        const container = document.getElementById('protocolList');
        if (this.protocols.length === 0) {
            container.innerHTML = '<div class="empty-state"><div class="empty-icon">📋</div><p>Žádné protokoly</p></div>';
            return;
        }
        
        container.innerHTML = this.protocols.map(p => {
            const typeInfo = this.typeLabels[p.type] || this.typeLabels.handover;
            return `
                <div class="protocol-item ${p.id === this.currentId ? 'active' : ''}" onclick="App.loadProtocol('${p.id}')">
                    <div class="protocol-item-header">
                        <span class="protocol-item-number">${p.number || '-'}</span>
                        <span class="protocol-item-type ${typeInfo.class}">${typeInfo.name}</span>
                    </div>
                    <div class="protocol-item-title">${p.subject || 'Bez názvu'}</div>
                    <div class="protocol-item-meta">${p.customer?.name || '-'} • ${this.formatDate(p.date)}</div>
                </div>
            `;
        }).join('');
    },
    
    // Items
    renderItems() {
        document.getElementById('itemsBody').innerHTML = this.items.map((item, i) => `
            <tr>
                <td><input type="text" value="${item.description}" onchange="App.updateItem(${i}, 'description', this.value)" placeholder="Popis položky"></td>
                <td><input type="number" value="${item.quantity}" min="1" onchange="App.updateItem(${i}, 'quantity', this.value)"></td>
                <td>
                    <select onchange="App.updateItem(${i}, 'unit', this.value)">
                        <option value="ks" ${item.unit === 'ks' ? 'selected' : ''}>ks</option>
                        <option value="m" ${item.unit === 'm' ? 'selected' : ''}>m</option>
                        <option value="kg" ${item.unit === 'kg' ? 'selected' : ''}>kg</option>
                        <option value="hod" ${item.unit === 'hod' ? 'selected' : ''}>hod</option>
                        <option value="kpl" ${item.unit === 'kpl' ? 'selected' : ''}>kpl</option>
                    </select>
                </td>
                <td><input type="text" value="${item.serial || ''}" onchange="App.updateItem(${i}, 'serial', this.value)" placeholder="S/N"></td>
                <td>
                    <select onchange="App.updateItem(${i}, 'condition', this.value)">
                        <option value="ok" ${item.condition === 'ok' ? 'selected' : ''}>OK</option>
                        <option value="damaged" ${item.condition === 'damaged' ? 'selected' : ''}>Poškozeno</option>
                        <option value="used" ${item.condition === 'used' ? 'selected' : ''}>Použité</option>
                    </select>
                </td>
                <td><button class="btn-remove" onclick="App.removeItem(${i})">×</button></td>
            </tr>
        `).join('');
    },
    
    addItem() {
        this.items.push({ id: Date.now(), description: '', quantity: 1, unit: 'ks', serial: '', condition: 'ok' });
        this.renderItems();
    },
    
    updateItem(index, field, value) {
        this.items[index][field] = value;
    },
    
    removeItem(index) {
        this.items.splice(index, 1);
        this.renderItems();
    },
    
    // Checklist
    renderChecklist() {
        document.getElementById('checklistBody').innerHTML = this.checklist.map((item, i) => `
            <div class="checklist-item">
                <input type="checkbox" id="check-${i}" ${item.checked ? 'checked' : ''} onchange="App.updateCheck(${i}, 'checked', this.checked)">
                <label for="check-${i}">${item.text}</label>
                <select onchange="App.updateCheck(${i}, 'note', this.value)">
                    <option value="" ${!item.note ? 'selected' : ''}>-</option>
                    <option value="OK" ${item.note === 'OK' ? 'selected' : ''}>✓ OK</option>
                    <option value="N/A" ${item.note === 'N/A' ? 'selected' : ''}>N/A</option>
                    <option value="Závada" ${item.note === 'Závada' ? 'selected' : ''}>⚠ Závada</option>
                </select>
                <button class="btn-remove" onclick="App.removeCheck(${i})" style="font-size: 0.9rem;">×</button>
            </div>
        `).join('');
    },
    
    addCheckItem() {
        const input = document.getElementById('newCheckItem');
        const text = input.value.trim();
        if (!text) return;
        this.checklist.push({ id: Date.now(), text, checked: false, note: '' });
        this.renderChecklist();
        input.value = '';
    },
    
    updateCheck(index, field, value) {
        this.checklist[index][field] = value;
    },
    
    removeCheck(index) {
        this.checklist.splice(index, 1);
        this.renderChecklist();
    },
    
    // Signatures
    initSignatureCanvas() {
        const canvas = document.getElementById('signatureCanvas');
        const ctx = canvas.getContext('2d');
        
        canvas.addEventListener('mousedown', (e) => this.startDrawing(e, ctx, canvas));
        canvas.addEventListener('mousemove', (e) => this.draw(e, ctx, canvas));
        canvas.addEventListener('mouseup', () => this.isDrawing = false);
        canvas.addEventListener('mouseout', () => this.isDrawing = false);
        
        canvas.addEventListener('touchstart', (e) => { e.preventDefault(); this.startDrawing(e.touches[0], ctx, canvas); });
        canvas.addEventListener('touchmove', (e) => { e.preventDefault(); this.draw(e.touches[0], ctx, canvas); });
        canvas.addEventListener('touchend', () => this.isDrawing = false);
    },
    
    startDrawing(e, ctx, canvas) {
        this.isDrawing = true;
        const rect = canvas.getBoundingClientRect();
        ctx.beginPath();
        ctx.moveTo(e.clientX - rect.left, e.clientY - rect.top);
    },
    
    draw(e, ctx, canvas) {
        if (!this.isDrawing) return;
        const rect = canvas.getBoundingClientRect();
        ctx.lineTo(e.clientX - rect.left, e.clientY - rect.top);
        ctx.strokeStyle = '#000';
        ctx.lineWidth = 2;
        ctx.lineCap = 'round';
        ctx.stroke();
    },
    
    openSignature(target) {
        this.signatureTarget = target;
        this.clearSignature();
        document.getElementById('signatureModal').classList.add('active');
    },
    
    closeSignature() {
        document.getElementById('signatureModal').classList.remove('active');
    },
    
    clearSignature() {
        const canvas = document.getElementById('signatureCanvas');
        const ctx = canvas.getContext('2d');
        ctx.clearRect(0, 0, canvas.width, canvas.height);
    },
    
    saveSignature() {
        const canvas = document.getElementById('signatureCanvas');
        const dataUrl = canvas.toDataURL('image/png');
        this.signatures[this.signatureTarget] = dataUrl;
        this.renderSignatures();
        this.closeSignature();
        this.updateUI();
    },
    
    renderSignatures() {
        ['supplier', 'customer'].forEach(type => {
            const container = document.getElementById(`signature${type.charAt(0).toUpperCase() + type.slice(1)}`);
            if (this.signatures[type]) {
                container.innerHTML = `<img src="${this.signatures[type]}" class="signature-preview" alt="Podpis">`;
                container.classList.add('has-signature');
                container.onclick = null;
            } else {
                container.innerHTML = `
                    <span style="font-size: 2rem; opacity: 0.3;">✍️</span>
                    <span style="font-size: 0.8rem; color: var(--text-muted);">Klikněte pro podpis</span>
                `;
                container.classList.remove('has-signature');
                container.onclick = () => this.openSignature(type);
            }
        });
    },
    
    // Preview & Export
    preview() {
        this.saveProtocol();
        document.getElementById('editor').style.display = 'none';
        document.getElementById('printPreviewContainer').style.display = 'block';
        this.renderPreview();
    },
    
    closePreview() {
        document.getElementById('editor').style.display = 'block';
        document.getElementById('printPreviewContainer').style.display = 'none';
    },
    
    renderPreview() {
        const data = this.collectData();
        const typeInfo = this.typeLabels[data.type] || this.typeLabels.handover;
        
        document.getElementById('printPreview').innerHTML = `
            <div class="print-header">
                <div>
                    <div class="print-title">${typeInfo.name.toUpperCase()}</div>
                    <div class="print-number">č. ${data.number}</div>
                </div>
                <div class="print-type-badge ${typeInfo.class}">${typeInfo.name}</div>
            </div>
            
            <div class="print-parties">
                <div class="print-party supplier">
                    <div class="print-party-label">Předávající / Dodavatel</div>
                    <div class="print-party-name">${data.supplier.name || '-'}</div>
                    <div class="print-party-details">
                        ${data.supplier.address ? `<div>${data.supplier.address}</div>` : ''}
                        ${data.supplier.ico ? `<div>IČO: ${data.supplier.ico}</div>` : ''}
                        ${data.supplier.person ? `<div>Zastoupený: ${data.supplier.person}</div>` : ''}
                    </div>
                </div>
                <div class="print-party customer">
                    <div class="print-party-label">Přebírající / Objednavatel</div>
                    <div class="print-party-name">${data.customer.name || '-'}</div>
                    <div class="print-party-details">
                        ${data.customer.address ? `<div>${data.customer.address}</div>` : ''}
                        ${data.customer.ico ? `<div>IČO: ${data.customer.ico}</div>` : ''}
                        ${data.customer.person ? `<div>Zastoupený: ${data.customer.person}</div>` : ''}
                    </div>
                </div>
            </div>
            
            <div class="print-meta">
                <div class="print-meta-item">
                    <label>Číslo protokolu</label>
                    <span>${data.number}</span>
                </div>
                <div class="print-meta-item">
                    <label>Datum</label>
                    <span>${this.formatDate(data.date)}</span>
                </div>
                <div class="print-meta-item">
                    <label>Místo</label>
                    <span>${data.place || '-'}</span>
                </div>
                <div class="print-meta-item">
                    <label>Předmět</label>
                    <span>${data.subject || '-'}</span>
                </div>
            </div>
            
            ${data.items.filter(i => i.description).length > 0 ? `
                <div class="print-section">
                    <div class="print-section-title">📦 Předmět předání</div>
                    <table class="print-table">
                        <thead>
                            <tr>
                                <th>Popis</th>
                                <th>Množství</th>
                                <th>S/N</th>
                                <th>Stav</th>
                            </tr>
                        </thead>
                        <tbody>
                            ${data.items.filter(i => i.description).map(item => `
                                <tr>
                                    <td>${item.description}</td>
                                    <td>${item.quantity} ${item.unit}</td>
                                    <td>${item.serial || '-'}</td>
                                    <td>${item.condition === 'ok' ? '✓ OK' : item.condition === 'damaged' ? '⚠ Poškozeno' : 'Použité'}</td>
                                </tr>
                            `).join('')}
                        </tbody>
                    </table>
                </div>
            ` : ''}
            
            ${data.checklist.length > 0 ? `
                <div class="print-section">
                    <div class="print-section-title">✅ Kontrolní seznam</div>
                    <div class="print-checklist">
                        ${data.checklist.map(item => `
                            <div class="print-checklist-item">
                                <span class="print-checkbox ${item.checked ? 'checked' : ''}">${item.checked ? '✓' : ''}</span>
                                <span style="flex: 1;">${item.text}</span>
                                <span style="font-weight: 600;">${item.note || '-'}</span>
                            </div>
                        `).join('')}
                    </div>
                </div>
            ` : ''}
            
            ${data.notes ? `
                <div class="print-section">
                    <div class="print-section-title">📝 Poznámky a závady</div>
                    <div class="print-notes">${data.notes}</div>
                </div>
            ` : ''}
            
            <div class="print-signatures">
                <div class="print-signature-box">
                    ${this.signatures.supplier ? `<img src="${this.signatures.supplier}" class="print-signature-img">` : ''}
                    <div class="print-signature-line"></div>
                    <div class="print-signature-label">Podpis předávajícího</div>
                    <div class="print-signature-name">${data.supplier.person || ''}</div>
                </div>
                <div class="print-signature-box">
                    ${this.signatures.customer ? `<img src="${this.signatures.customer}" class="print-signature-img">` : ''}
                    <div class="print-signature-line"></div>
                    <div class="print-signature-label">Podpis přebírajícího</div>
                    <div class="print-signature-name">${data.customer.person || ''}</div>
                </div>
            </div>
            
            <div class="print-footer">
                Protokol vygenerován: ${new Date().toLocaleDateString('cs-CZ')} • ${data.supplier.name || ''}
            </div>
        `;
    },
    
    exportPDF() {
        this.saveProtocol();
        this.renderPreview();
        
        const element = document.getElementById('printPreview');
        const number = document.getElementById('protocolNumber').value || 'protokol';
        
        const opt = {
            margin: 0,
            filename: `${number}.pdf`,
            image: { type: 'jpeg', quality: 0.98 },
            html2canvas: { scale: 2, useCORS: true },
            jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
        };
        
        html2pdf().set(opt).from(element).save().then(() => {
            this.showToast('PDF vytvořeno', 'success');
        });
    },
    
    exportAll() {
        const data = JSON.stringify(this.protocols, null, 2);
        const blob = new Blob([data], { type: 'application/json' });
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = `protokoly-export-${new Date().toISOString().split('T')[0]}.json`;
        a.click();
        URL.revokeObjectURL(url);
        this.showToast('Export dokončen', 'success');
    },
    
    // Helpers
    formatDate(date) {
        if (!date) return '-';
        return new Date(date).toLocaleDateString('cs-CZ');
    },
    
    showToast(message, type = '') {
        const toast = document.getElementById('toast');
        toast.textContent = message;
        toast.className = 'toast show' + (type ? ' ' + type : '');
        setTimeout(() => toast.classList.remove('show'), 3000);
    }
};

document.addEventListener('DOMContentLoaded', () => App.init());
</script>
</body>
</html>
