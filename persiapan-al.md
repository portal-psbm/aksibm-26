---
layout: default
title: Persiapan AL
permalink: /persiapan-al/
---

<style>
  .al-header { background: linear-gradient(135deg, #0d47a1 0%, #1976d2 100%); color: white; padding: 24px; border-radius: 12px; margin-bottom: 20px; box-shadow: 0 4px 12px rgba(0,0,0,0.15); }
  .al-header h1 { margin: 0; font-size: 1.6rem; }
  .al-header .subtitle { opacity: 0.9; font-size: 0.95rem; margin-top: 4px; }
  .al-header .h-countdown { display: inline-block; background: #ff6f00; padding: 6px 14px; border-radius: 20px; font-weight: 700; margin-top: 8px; font-size: 0.9rem; }
  .al-nav { display: flex; flex-wrap: wrap; gap: 6px; background: #f1f5f9; padding: 10px; border-radius: 10px; margin-bottom: 20px; border: 1px solid #e0e0e0; }
  .al-nav button { flex: 1; min-width: 100px; padding: 10px 14px; background: transparent; border: none; border-radius: 6px; cursor: pointer; font-weight: 600; color: #455a64; transition: all 0.2s; font-size: 0.88rem; }
  .al-nav button:hover { background: #e3f2fd; color: #0d47a1; }
  .al-nav button.active { background: #0d47a1; color: white; box-shadow: 0 2px 6px rgba(13,71,161,0.3); }
  .al-content { min-height: 500px; }
  .al-panel { display: none; animation: fadeIn 0.3s ease; }
  .al-panel.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }
  .card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 16px; margin: 16px 0; }
  .stat-card { background: white; border-radius: 10px; padding: 18px; box-shadow: 0 2px 8px rgba(0,0,0,0.08); border-left: 4px solid #0d47a1; }
  .stat-card .label { font-size: 0.85rem; color: #666; margin-bottom: 6px; }
  .stat-card .value { font-size: 1.8rem; font-weight: 700; color: #0d47a1; }
  .progress-row { display: flex; align-items: center; gap: 12px; padding: 10px 0; border-bottom: 1px solid #f0f0f0; }
  .progress-row .label { width: 60px; font-weight: 600; color: #0d47a1; }
  .progress-row .bar { flex: 1; height: 14px; background: #e0e0e0; border-radius: 7px; overflow: hidden; }
  .progress-row .bar-fill { height: 100%; background: linear-gradient(to right, #4caf50, #81c784); border-radius: 7px; transition: width 0.6s; }
  .progress-row .bar-fill.review { background: linear-gradient(to right, #ff9800, #ffb74d); }
  .progress-row .percent { width: 40px; font-weight: 600; text-align: right; }
  .progress-row .status { width: 80px; text-align: center; font-size: 0.75rem; font-weight: 700; padding: 3px 8px; border-radius: 12px; }
  .status-ready { background: #e8f5e9; color: #2e7d
