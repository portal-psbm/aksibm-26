<style>
/* ===== MODERN CABINET & MAIN TABS ===== */
.ev-cabinet { 
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%); 
  padding: 20px 20px 0 20px; 
  border-radius: 16px 16px 0 0; 
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08); 
  position: relative; 
  border: 1px solid #e2e8f0; 
  border-bottom: none; 
}
.ev-shelf { 
  display: flex; 
  gap: 8px; 
  padding: 0 4px; 
  position: relative; 
  z-index: 10; 
  overflow-x: auto; 
  scrollbar-width: none; 
}
.ev-shelf::-webkit-scrollbar { display: none; }

.ev-tab { 
  position: relative;
  flex: 1;
  min-width: 0;
  padding: 14px 16px 18px 16px; 
  background: white;
  border-radius: 12px 12px 0 0;
  border: 1px solid #e2e8f0;
  border-bottom: none;
  cursor: pointer; 
  text-align: center; 
  font-weight: 600; 
  font-size: 0.85rem; 
  line-height: 1.3; 
  color: #64748b; 
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); 
  transform: translateY(2px);
  box-shadow: 0 -2px 6px rgba(0,0,0,0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
}
.ev-tab::before { 
  content: ''; 
  position: absolute; 
  top: 0; left: 0; right: 0; 
  height: 3px; 
  background: transparent; 
  border-radius: 12px 12px 0 0; 
  transition: all 0.3s ease; 
}
.ev-tab:hover { 
  background: #f8fafc; 
  transform: translateY(0); 
  color: #0d47a1; 
  box-shadow: 0 -4px 12px rgba(0,0,0,0.06);
}
.ev-tab:hover::before { background: #cbd5e1; }

.ev-tab.active { 
  background: white; 
  color: #0d47a1; 
  transform: translateY(-4px); 
  z-index: 20; 
  border-color: #0d47a1; 
  box-shadow: 0 -6px 20px rgba(13, 71, 161, 0.15); 
  font-weight: 700; 
}
.ev-tab.active::before { 
  background: linear-gradient(90deg, #0d47a1, #1565c0); 
  height: 4px; 
}
.ev-tab .tab-icon { font-size: 1.3rem; }
.ev-tab .tab-label { font-size: 0.75rem; opacity: 0.8; }
.ev-tab.active .tab-label { opacity: 1; }

/* SESI 2 - BIRU MUDA */
.ev-tab.sesi2.active { 
  color: #0288d1; 
  border-color: #0288d1; 
  box-shadow: 0 -6px 20px rgba(2, 136, 209, 0.15); 
}
.ev-tab.sesi2.active::before { 
  background: linear-gradient(90deg, #0288d1, #29b6f6); 
}

/* ===== MODERN SUB-NAV (SEGMENTED CONTROL) ===== */
.criteria-nav { 
  display: flex; 
  gap: 6px; 
  margin-bottom: 20px; 
  flex-wrap: wrap; 
  padding: 8px;
  background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  box-shadow: inset 0 2px 4px rgba(0,0,0,0.02);
}
.criteria-nav button { 
  position: relative;
  padding: 8px 12px; 
  background: white;
  border: 1.5px solid #e2e8f0;
  border-radius: 8px;
  cursor: pointer; 
  font-weight: 600; 
  color: #64748b; 
  font-size: 0.75rem;
  transition: all 0.25s ease;
  box-shadow: 0 1px 2px rgba(0,0,0,0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
  min-width: 65px;
}
.criteria-nav button small {
  font-size: 0.62rem;
  font-weight: 500;
  opacity: 0.7;
}
.criteria-nav button:hover { 
  transform: translateY(-1px);
  border-color: #0d47a1;
  color: #0d47a1;
  box-shadow: 0 3px 8px rgba(13, 71, 161, 0.1);
}
.criteria-nav button.active { 
  background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%);
  color: white;
  border-color: #0d47a1;
  box-shadow: 0 3px 10px rgba(13, 71, 161, 0.25);
  transform: translateY(-1px);
}
.criteria-nav button.active small { opacity: 0.9; }

/* SESI 2 SUB-NAV */
.criteria-nav.ledps-nav button:hover {
  border-color: #0288d1;
  color: #0288d1;
  box-shadow: 0 3px 8px rgba(2, 136, 209, 0.1);
}
.criteria-nav.ledps-nav button.active { 
  background: linear-gradient(135deg, #0288d1 0%, #29b6f6 100%);
  border-color: #0288d1;
  box-shadow: 0 3px 10px rgba(2, 136, 209, 0.25);
}
.criteria-nav button.bab3-btn {
  background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%);
  border-color: #ffcc80;
  color: #e65100;
}
.criteria-nav button.bab3-btn:hover {
  border-color: #e65100;
  color: #e65100;
}
.criteria-nav button.bab3-btn.active {
  background: linear-gradient(135deg, #e65100 0%, #f57c00 100%);
  color: white;
  border-color: #e65100;
  box-shadow: 0 3px 10px rgba(230, 81, 0, 0.25);
}

/* ===== KONTEN & LAYOUT (TIDAK DIUBAH) ===== */
.ev-content { background: #ffffff; border: 1px solid #e0e0e0; border-top: 3px solid #0d47a1; border-radius: 0 0 16px 16px; padding: 24px; min-height: 500px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); position: relative; z-index: 5; margin-top: -1px; }
.ev-panel { display: none; animation: fadeIn 0.3s ease; }
.ev-panel.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

.session-header { padding: 20px; border-radius: 12px; margin-bottom: 16px; color: white; }
.session-header.sesi1 { background: linear-gradient(135deg, #1565c0 0%, #0d47a1 100%); }
.session-header.sesi2 { background: linear-gradient(135deg, #0288d1 0%, #01579b 100%); }
.session-header h2 { margin: 0 0 6px 0; font-size: 1.3rem; }
.session-header .subtitle { opacity: 0.95; font-size: 0.88rem; margin-bottom: 10px; }
.session-header .tag { display: inline-block; background: rgba(255,255,255,0.25); padding: 4px 12px; border-radius: 12px; font-size: 0.72rem; font-weight: 700; margin-bottom: 8px; letter-spacing: 0.5px; }

.lkps-table-panel { display: none; animation: fadeIn 0.3s ease; }
.lkps-table-panel.active { display: block; }
.ledps-criteria { display: none; animation: fadeIn 0.3s ease; }
.ledps-criteria.active { display: block; }

.lkps-section { margin-bottom: 20px; }
.lkps-section h3 { color: #0d47a1; border-left: 4px solid #0d47a1; padding-left: 12px; margin-bottom: 12px; font-size: 1.05rem; }
.lkps-section.ledps h3 { color: #0288d1; border-left-color: #0288d1; }

.table-responsive { overflow-x: auto; border: 1px solid #e0e0e0; border-radius: 8px; margin-bottom: 16px; }
.lkps-table { width: 100%; border-collapse: collapse; font-size: 0.82rem; min-width: 600px; }
.lkps-table th, .lkps-table td { border: 1px solid #e0e0e0; padding: 8px 10px; text-align: left; vertical-align: top; }
.lkps-table th { background-color: #f1f5f9; font-weight: 600; color: #0d47a1; position: sticky; top: 0; z-index: 1; }
.lkps-table tr:nth-child(even) { background-color: #f8fafc; }
.lkps-table tr:hover { background-color: #e3f2fd; }
.highlight-data { background-color: #fff8e1 !important; font-weight: 600; color: #e65100; }
.link-cell a { color: #0d47a1; text-decoration: none; word-break: break-all; font-weight: 600; }
.link-cell a:hover { text-decoration: underline; }

.summary-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 10px; margin: 16px 0; }
.summary-card { background: white; border: 1px solid #e0e0e0; border-left: 4px solid #0d47a1; border-radius: 8px; padding: 12px; transition: all 0.2s; }
.summary-card:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); transform: translateY(-2px); }
.summary-card .sc-label { font-size: 0.72rem; color: #666; text-transform: uppercase; letter-spacing: 0.5px; }
.summary-card .sc-value { font-size: 1.3rem; font-weight: 800; color: #0d47a1; margin: 4px 0; }
.summary-card .sc-desc { font-size: 0.75rem; color: #555; }

.info-box { background: #e3f2fd; border-left: 4px solid #0d47a1; padding: 12px 16px; border-radius: 6px; margin-bottom: 20px; font-size: 0.88rem; color: #0d47a1; }
.info-box.ledps { background: #e1f5fe; border-left-color: #0288d1; color: #01579b; }
.info-box strong { color: inherit; filter: brightness(0.7); }

.led-card { background: white; border: 1px solid #e0e0e0; border-radius: 10px; padding: 14px 16px; margin-bottom: 10px; border-left: 4px solid #0288d1; }
.led-card h4 { color: #0288d1; margin: 0 0 8px 0; font-size: 0.92rem; }
.led-card p { color: #555; font-size: 0.85rem; line-height: 1.5; margin: 0 0 8px 0; }
.led-card ul { margin: 8px 0; padding-left: 20px; font-size: 0.82rem; color: #555; }
.led-card li { margin-bottom: 4px; line-height: 1.5; }

.evidence-link { display: inline-flex; align-items: center; gap: 4px; background: #e1f5fe; color: #0288d1; padding: 4px 10px; border-radius: 12px; font-size: 0.75rem; font-weight: 600; text-decoration: none; margin-top: 8px; margin-right: 6px; }
.evidence-link:hover { background: #b3e5fc; }

.table-link-btn { display: inline-flex; align-items: center; gap: 6px; padding: 6px 14px; background: linear-gradient(135deg, #0d47a1 0%, #1565c0 100%); color: white; border-radius: 6px; text-decoration: none; font-weight: 600; font-size: 0.78rem; transition: all 0.2s; margin: 4px 4px 4px 0; box-shadow: 0 2px 6px rgba(13, 71, 161, 0.2); }
.table-link-btn:hover { background: linear-gradient(135deg, #1565c0 0%, #1976d2 100%); transform: translateY(-1px); box-shadow: 0 4px 10px rgba(13, 71, 161, 0.3); }
.table-link-btn.secondary { background: linear-gradient(135deg, #455a64 0%, #546e7a 100%); box-shadow: 0 2px 6px rgba(69, 90, 100, 0.2); }
.table-link-btn.secondary:hover { background: linear-gradient(135deg, #546e7a 0%, #607d8b 100%); }
.table-link-btn.success { background: linear-gradient(135deg, #2e7d32 0%, #388e3c 100%); box-shadow: 0 2px 6px rgba(46, 125, 50, 0.2); }
.table-link-btn.success:hover { background: linear-gradient(135deg, #388e3c 0%, #43a047 100%); }
.table-link-btn .btn-icon { font-size: 0.9rem; }

.swot-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 16px 0; }
.swot-card { padding: 14px; border-radius: 10px; border: 2px solid; }
.swot-card.strength { background: #e8f5e9; border-color: #4caf50; }
.swot-card.weakness { background: #fff3e0; border-color: #ff9800; }
.swot-card.opportunity { background: #e3f2fd; border-color: #2196f3; }
.swot-card.threat { background: #ffebee; border-color: #f44336; }
.swot-card h4 { margin: 0 0 8px 0; font-size: 0.9rem; }
.swot-card ul { margin: 0; padding-left: 18px; font-size: 0.82rem; }
.swot-card ul li { padding: 2px 0; }

@media (max-width: 767px) {
.ev-shelf { gap: 4px; padding-bottom: 6px; overflow-x: auto; -webkit-overflow-scrolling: touch; scrollbar-width: none; }
.ev-shelf::-webkit-scrollbar { display: none; }
.ev-tab { min-width: 100px; flex: 0 0 auto; font-size: 0.75rem; padding: 12px 10px; }
.ev-content { padding: 16px; }
.summary-grid { grid-template-columns: 1fr 1fr; }
.swot-grid { grid-template-columns: 1fr; }
.criteria-nav { gap: 4px; padding: 6px; }
.criteria-nav button { padding: 6px 8px; font-size: 0.7rem; min-width: 60px; }
}
</style>
