<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sopaan · Algebraic expressions and equations</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,700&family=Source+Sans+3:wght@400;600;700&family=IBM+Plex+Mono:wght@500;600&display=swap">
<style>
  html,body{margin:0;} img{max-width:100%;} [hidden]{display:none !important;}
  :root{
    --navy:#16264A; --navy-2:#1F3B6B; --gold:#C79A3E; --gold-soft:#F3E7C9;
    --paper:#FBF9F4; --paper-2:#F1EAD8; --card:#FFFFFF;
    --ink:#211E1A; --ink-soft:#655D4C; --rule:#E4DCC8;
    --success:#2E8B57; --success-soft:#E1F2E7;
    --danger:#BF4B45; --danger-soft:#FAE3E1;
    --locked:#C7BEA9;
    --focus:#1F3B6B;
    --accent-text:#1F3B6B; --retry-text:#8A661F;
    color-scheme:light;
  }
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){
      --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
      --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
      --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
      --success:#7BC79A; --success-soft:#1B2E22;
      --danger:#E38884; --danger-soft:#331D1B;
      --locked:#4A4436;
      --focus:#E0B75B;
      --accent-text:#E0B75B; --retry-text:#E0B75B;
      color-scheme:dark;
    }
  }
  :root[data-theme="dark"]{
    --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
    --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
    --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
    --success:#7BC79A; --success-soft:#1B2E22;
    --danger:#E38884; --danger-soft:#331D1B;
    --locked:#4A4436;
    --focus:#E0B75B;
    --accent-text:#E0B75B; --retry-text:#E0B75B;
    color-scheme:dark;
  }

  *{box-sizing:border-box;}
  body{background:var(--paper); color:var(--ink); font-family:'Source Sans 3',-apple-system,'Segoe UI',sans-serif; padding-inline:0; padding-block:0;}
  h1,h2,h3{font-family:'Fraunces',Georgia,serif; text-wrap:balance; margin:0;}
  .num{font-family:'IBM Plex Mono',ui-monospace,monospace; font-variant-numeric:tabular-nums;}

  header.brand{
    background:linear-gradient(155deg,var(--navy) 0%, var(--navy-2) 100%);
    color:#F4EFDF; padding-block:calc(20px + env(safe-area-inset-top,0px)) 18px; padding-inline:20px;
  }
  .brand-row{display:flex; align-items:center; gap:12px; max-width:900px; margin:0 auto;}
  .crest{
    width:42px; height:42px; border-radius:10px; background:var(--gold); color:var(--navy);
    display:flex; align-items:center; justify-content:center; font-family:'Fraunces',serif; font-weight:700; font-size:18px; flex-shrink:0;
  }
  .brand-name{font-size:12px; letter-spacing:.08em; text-transform:uppercase; color:var(--gold); font-weight:700;}
  .series-name{font-size:19px; font-weight:700; font-family:'Fraunces',serif;}
  .chapter-eyebrow{max-width:900px; margin:14px auto 0; font-size:12px; letter-spacing:.06em; text-transform:uppercase; color:#AEB9D6;}
  .chapter-title{font-size:28px; max-width:900px; margin:2px auto 0;}
  .chapter-sub{font-size:14.5px; color:var(--gold); font-weight:700; max-width:900px; margin:3px auto 0;}

  .chapter-progress{max-width:900px; margin:14px auto 0; display:flex; align-items:center; gap:10px;}
  .cp-track{flex:1; height:6px; border-radius:99px; background:rgba(255,255,255,.18); overflow:hidden;}
  .cp-fill{height:100%; background:var(--gold); border-radius:99px; transition:width .3s ease;}
  .cp-label{font-size:11.5px; color:#CFD7EA; white-space:nowrap;}

  .tabbar{position:sticky; top:env(safe-area-inset-top,0px); z-index:15; background:var(--paper); border-bottom:1px solid var(--rule); overflow-x:auto; white-space:nowrap;}
  .tabbar-inner{max-width:900px; margin:0 auto; display:flex; padding-inline:16px;}
  .tab-btn{font-family:inherit; font-size:14px; font-weight:600; color:var(--ink-soft); background:none; border:none; padding:13px 16px; cursor:pointer; position:relative; flex-shrink:0;}
  .tab-btn.active{color:var(--accent-text);}
  .tab-btn.active::after{content:''; position:absolute; left:12px; right:12px; bottom:0; height:3px; background:var(--gold); border-radius:3px 3px 0 0;}
  .tab-count{font-size:11px; color:var(--ink-soft); margin-left:5px;}

  .slide-progress{max-width:900px; margin:0 auto; padding:10px 16px 0; display:flex; align-items:center; gap:10px;}
  .sp-track{flex:1; height:5px; border-radius:99px; background:var(--rule); overflow:hidden;}
  .sp-fill{height:100%; background:var(--accent-text); border-radius:99px; transition:width .3s ease;}
  .sp-label{font-size:12px; color:var(--ink-soft); white-space:nowrap; font-weight:600;}

  .wrap{max-width:900px; margin:0 auto; padding:16px 16px calc(110px + env(safe-area-inset-bottom,0px));}

  .qcard{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px;}
  .qhead{display:flex; align-items:flex-start; gap:10px; margin-bottom:10px;}
  .qnum{width:32px; height:32px; border-radius:8px; background:var(--gold-soft); color:var(--accent-text); display:flex; align-items:center; justify-content:center; font-weight:700; font-family:'Fraunces',serif; flex-shrink:0; font-size:14px;}
  .qtext{font-size:16px; line-height:1.55; flex:1;}
  .qtag{font-size:10.5px; color:var(--gold); background:var(--gold-soft); padding:2px 7px; border-radius:99px; font-weight:700; margin-left:6px; white-space:nowrap;}
  .marks-pill{font-size:11px; font-weight:700; color:var(--ink-soft); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; margin-left:auto; flex-shrink:0; white-space:nowrap;}
  .step-badge{font-size:11px; font-weight:700; color:var(--accent-text); background:var(--paper-2); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; display:inline-block; margin-bottom:12px;}

  .options{display:flex; flex-direction:column; gap:8px; margin-top:10px;}
  .opt{display:flex; align-items:center; gap:10px; padding:11px 12px; border:1.5px solid var(--rule); border-radius:10px; cursor:pointer; font-size:15px; background:var(--paper);}
  .opt input{accent-color:var(--navy-2);}
  .opt.is-correct{border-color:var(--success); background:var(--success-soft);}
  .opt.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .opt.locked{cursor:not-allowed;}

  .subpart-label{font-weight:700; font-size:12.5px; color:var(--accent-text); text-transform:uppercase; letter-spacing:.03em; margin:14px 0 6px;}
  .or-divider{text-align:center; font-size:11px; font-weight:700; letter-spacing:.08em; color:var(--ink-soft); margin:8px 0;}

  .steps{display:flex; flex-direction:column; gap:10px;}
  .step-line{font-size:14.5px; line-height:1.9; background:var(--paper); border:1px dashed var(--rule); border-radius:10px; padding:9px 12px;}
  .step-line.resolved{opacity:.9;}
  .blank-input{font-family:'IBM Plex Mono',monospace; font-size:14px; border:1.5px solid var(--rule); border-radius:6px; padding:3px 8px; width:120px; background:var(--card); color:var(--ink); margin:0 2px;}
  .blank-input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .blank-input.is-correct{border-color:var(--success); background:var(--success-soft);}
  .blank-input.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .blank-input[disabled]{opacity:.85;}
  .reveal-note{font-size:12px; color:var(--danger); padding-left:2px; margin-top:-2px;}

  .feedback{font-size:13.5px; padding:10px 12px; border-radius:9px; margin-top:14px; display:none;}
  .feedback.show{display:block;}
  .feedback.ok{background:var(--success-soft); color:var(--success);}
  .feedback.retry{background:var(--gold-soft); color:var(--retry-text);}
  .feedback.reveal{background:var(--danger-soft); color:var(--danger);}
  .feedback.err{background:var(--danger-soft); color:var(--danger);}
  .attempts-dots{display:inline-flex; gap:4px; margin-left:2px;}
  .attempts-dots span{width:6px; height:6px; border-radius:50%; background:var(--ink-soft); opacity:.3; display:inline-block;}
  .attempts-dots span.used{opacity:1; background:var(--danger);}

  .ar-box{background:var(--paper-2); border-radius:10px; padding:10px 12px; margin-bottom:12px; font-size:13px; color:var(--ink-soft);}

  .navbar{
    position:fixed; left:0; right:0; bottom:0; z-index:30; background:var(--paper);
    border-top:1px solid var(--rule); padding:10px 16px calc(10px + env(safe-area-inset-bottom,0px));
  }
  .navbar-inner{max-width:900px; margin:0 auto; display:flex; gap:8px; flex-wrap:wrap; align-items:center;}
  .btn{font-family:inherit; font-size:13.5px; font-weight:700; padding:10px 14px; border-radius:9px; border:1.5px solid var(--rule); background:var(--card); color:var(--ink); cursor:pointer;}
  .btn:hover{border-color:var(--navy-2);}
  .btn:disabled{opacity:.4; cursor:not-allowed;}
  .btn-primary{background:var(--navy-2); color:#fff; border-color:var(--navy-2);}
  .navbar .spacer{flex:1;}

  .fab{position:fixed; right:16px; bottom:calc(74px + env(safe-area-inset-bottom,0px)); background:var(--gold); color:var(--navy); border:none; border-radius:999px; padding:11px 16px; font-family:inherit; font-weight:700; font-size:13px; display:flex; align-items:center; gap:7px; cursor:pointer; box-shadow:0 6px 16px rgba(0,0,0,.18); z-index:35;}
  .fab-badge{background:rgba(255,255,255,.55); border-radius:99px; padding:1px 7px; font-size:11px;}

  .overlay{position:fixed; inset:0; background:rgba(20,18,14,.45); z-index:50; display:none; align-items:flex-end; justify-content:center;}
  .overlay.show{display:flex;}
  .palette{background:var(--card); width:min(480px,100%); max-height:78vh; overflow-y:auto; border-radius:18px 18px 0 0; padding:18px 18px calc(18px + env(safe-area-inset-bottom,0px)); border:1px solid var(--rule); border-bottom:none;}
  @media (min-width:640px){ .overlay{align-items:center;} .palette{border-radius:18px; border-bottom:1px solid var(--rule); max-height:74vh;} }
  .palette-head{display:flex; align-items:center; justify-content:space-between; margin-bottom:6px;}
  .palette-head h2{font-size:16px;}
  .palette-close{background:none; border:none; font-size:20px; color:var(--ink-soft); cursor:pointer; padding:4px;}
  .palette-legend{display:flex; gap:12px; flex-wrap:wrap; font-size:11px; color:var(--ink-soft); margin:10px 0 14px;}
  .palette-legend span{display:inline-flex; align-items:center; gap:5px;}
  .dot{width:9px; height:9px; border-radius:50%; display:inline-block;}
  .dot.correct{background:var(--success);} .dot.revealed{background:var(--danger);}
  .dot.skipped{background:var(--gold);} .dot.locked{background:var(--locked);}
  .dot.current{background:var(--navy-2);}
  .chip-grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(48px,1fr)); gap:8px;}
  .chip{border:1.5px solid var(--rule); border-radius:9px; padding:8px 4px; text-align:center; font-family:'IBM Plex Mono',monospace; font-size:12.5px; font-weight:600; cursor:pointer; background:var(--paper); color:var(--ink);}
  .chip[data-status="correct"]{border-color:var(--success); background:var(--success-soft); color:var(--success);}
  .chip[data-status="revealed"]{border-color:var(--danger); background:var(--danger-soft); color:var(--danger);}
  .chip[data-status="skipped"]{border-color:var(--gold); background:var(--gold-soft); color:var(--retry-text);}
  .chip[data-status="locked"]{border-color:var(--rule); color:var(--locked); cursor:not-allowed; background:var(--paper-2);}
  .chip[data-status="current"]{outline:2px solid var(--navy-2); outline-offset:1px;}

  .toast{position:fixed; left:50%; bottom:calc(140px + env(safe-area-inset-bottom,0px)); transform:translateX(-50%); background:var(--ink); color:var(--paper); padding:9px 16px; border-radius:99px; font-size:13px; opacity:0; pointer-events:none; transition:opacity .25s ease; z-index:60;}
  .toast.show{opacity:1;}

  .done-card{text-align:center; padding:36px 20px;}
  .done-card .big{font-size:38px; margin-bottom:6px;}
  .score-pills{display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin:16px 0;}
  .score-pill{padding:8px 16px; border-radius:99px; font-size:13px; font-weight:700;}

  footer.brandfoot{max-width:900px; margin:14px auto 0; padding:0 16px calc(110px + env(safe-area-inset-bottom,0px)); text-align:center; font-size:12px; color:var(--ink-soft);}

  .mode-pill{font-family:inherit; font-size:12.5px; font-weight:700; color:var(--navy); background:var(--gold); border:none; border-radius:99px; padding:6px 14px; cursor:pointer; margin-top:12px; display:inline-flex; align-items:center; gap:6px;}
  .mode-pick{display:flex; flex-direction:column; gap:14px; padding:8px 0 24px;}
  .mode-card{background:var(--card); border:1.5px solid var(--rule); border-radius:16px; padding:22px; cursor:pointer; text-align:left;}
  .mode-card:hover{border-color:var(--navy-2);}
  .mode-card .mode-icon{font-size:26px; margin-bottom:8px;}
  .mode-card h3{font-size:18px; margin-bottom:6px;}
  .mode-card p{font-size:13.5px; color:var(--ink-soft); line-height:1.5; margin:0;}
  .quiz-hint{font-size:12.5px; color:var(--ink-soft); background:var(--paper-2); border-radius:9px; padding:8px 12px; margin-bottom:14px;}
  .review-row{border:1px solid var(--rule); border-radius:10px; padding:11px 13px; margin-bottom:10px;}
  .review-tag{font-size:11.5px; font-weight:700; margin-bottom:4px; display:block;}
  .review-tag.ok{color:var(--success);} .review-tag.bad{color:var(--danger);} .review-tag.na{color:var(--ink-soft);}
  .review-q{font-size:13.5px; margin-bottom:6px; color:var(--ink-soft);}
  .review-ans{font-size:13px; margin-bottom:2px;}

  .who-row{max-width:900px; margin:12px auto 0; display:flex; flex-wrap:wrap; gap:8px; align-items:center;}
  .who-row .mode-pill{margin-top:0;}
  .who{display:inline-flex; flex-wrap:wrap; align-items:center; gap:6px; font-size:12.5px; color:#CFD7EA;}
  .who b{color:#F4EFDF;}
  .who button{font-family:inherit; font-size:12px; font-weight:700; color:#F4EFDF; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.22); border-radius:99px; padding:5px 11px; cursor:pointer;}
  .who button:hover{background:rgba(255,255,255,.2);}
  .login-card{max-width:460px; margin:8px auto 0; background:var(--card); border:1px solid var(--rule); border-radius:16px; padding:22px;}
  .login-card h2{font-size:21px; margin-bottom:4px;}
  .login-card p.lead{font-size:13.5px; color:var(--ink-soft); margin:0 0 16px; line-height:1.5;}
  .fld{display:flex; flex-direction:column; gap:5px; margin-bottom:12px;}
  .fld label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .fld input{font-family:inherit; font-size:15px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:9px; background:var(--paper); color:var(--ink);}
  .fld input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .fld-row{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
  .login-err{font-size:13px; color:var(--danger); background:var(--danger-soft); border-radius:8px; padding:8px 10px; margin-bottom:12px;}
  .login-note{font-size:12px; color:var(--ink-soft); margin-top:12px; line-height:1.5;}
  .known{margin:0 0 16px; display:flex; flex-direction:column; gap:6px;}
  .known-label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .known-btn{display:flex; justify-content:space-between; align-items:center; gap:10px; text-align:left; font-family:inherit; font-size:14.5px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:10px; background:var(--paper); color:var(--ink); cursor:pointer;}
  .known-btn:hover{border-color:var(--navy-2);}
  .known-btn small{font-size:12px; color:var(--ink-soft);}
  .rec-card{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px; margin-bottom:14px;}
  .rec-card h2{font-size:19px; margin-bottom:10px;}
  .rec-card h3{font-size:15px; margin:4px 0 8px;}
  .rec-table-wrap{overflow-x:auto;}
  .rec-table{width:100%; border-collapse:collapse; font-size:13.5px; font-variant-numeric:tabular-nums;}
  .rec-table th{text-align:left; font-size:11.5px; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); padding:6px 8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-table td{padding:8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-bar{display:inline-block; width:70px; height:6px; border-radius:99px; background:var(--rule); overflow:hidden; vertical-align:middle; margin-right:6px;}
  .rec-bar i{display:block; height:100%; background:var(--success);}
  .rec-empty{font-size:13.5px; color:var(--ink-soft);}
  .sec-sub{max-width:900px; margin:0 auto; padding:10px 16px 0; font-size:12.5px; font-weight:700; color:var(--accent-text); letter-spacing:.02em;}
  .opt{flex-wrap:wrap;}
  .opt-l{font-family:'IBM Plex Mono',monospace; font-size:13px; font-weight:600; color:var(--ink-soft);}
  .opt-t{flex:1; min-width:0;}
  .opt.is-chosen:not(.is-correct):not(.is-wrong){border-color:var(--navy-2); background:var(--gold-soft);}
  .opt-tag{font-size:11px; font-weight:700; padding:2px 8px; border-radius:99px; background:var(--card); border:1px solid currentColor; white-space:nowrap;}
  .opt.is-correct .opt-tag{color:var(--success);} .opt.is-wrong .opt-tag{color:var(--danger);} .opt.is-chosen:not(.is-correct):not(.is-wrong) .opt-tag{color:var(--accent-text);}
  .chosen{font-size:13.5px; margin-top:10px; padding:8px 12px; border-radius:9px;}
  .chosen.ok{background:var(--success-soft); color:var(--success);} .chosen.bad{background:var(--danger-soft); color:var(--danger);}
  .chosen + .chosen{margin-top:6px;}
  .solution{margin-top:14px; border:1px solid var(--rule); border-left:4px solid var(--gold); background:var(--paper-2); border-radius:10px; padding:12px 14px;}
  .sol-h{font-family:'Fraunces',Georgia,serif; font-weight:700; font-size:14px; color:var(--accent-text); margin-bottom:6px;}
  .sol-line{font-size:14.5px; line-height:1.7;}
  .rev-sol summary{cursor:pointer; font-size:12.5px; font-weight:700; color:var(--accent-text); margin-top:6px;}
  .rev-sol .solution{margin-top:8px;}
  .chapter-credit{max-width:900px; margin:4px auto 0; font-size:12px; color:#CFD7EA;}
  footer.brandfoot a{color:inherit;}
  .blank-input.wide{width:260px; max-width:100%; font-family:'Source Sans 3',sans-serif;}
  .blank-input.expr{width:170px; max-width:100%;}
  /*fix-layout*/ .cp-fill,.sp-fill{width:0;} .fld{min-width:0;} .fld input{width:100%; min-width:0; box-sizing:border-box;}
  .fig{margin:6px 0 10px; display:flex; justify-content:center;}
  .figsvg{width:100%; max-width:340px; height:auto; overflow:visible;}
  .figsvg .ln,.figsvg .arm{stroke:var(--ink); stroke-width:1.6; fill:none;}
  .figsvg .arm{stroke:var(--accent-text); stroke-width:2;}
  .figsvg .pt{fill:var(--ink);}
  .figsvg .lb{fill:var(--ink); font:600 13px 'Source Sans 3',sans-serif;}
  .figsvg .al{fill:var(--accent-text); font:700 12px 'Source Sans 3',sans-serif;}
  .figsvg .wg{fill:var(--gold-soft); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .wg2{fill:rgba(199,154,62,.35); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .ra{fill:none; stroke:var(--ink); stroke-width:1.2;}
  .figsvg .ahd{fill:var(--ink);}
  .figsvg .pr{fill:var(--paper-2); stroke:var(--ink-soft); stroke-width:1.2;}
  .figsvg .tk{stroke:var(--ink-soft); stroke-width:.8;}
  .figsvg .po{fill:var(--ink); font:600 8.5px 'IBM Plex Mono',monospace;}
  .figsvg .pi{fill:var(--danger); font:600 7.5px 'IBM Plex Mono',monospace;}
  .figsvg .sh{fill:var(--gold-soft); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh2{fill:rgba(199,154,62,.38); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh3{fill:rgba(199,154,62,.22); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .none{fill:none;}
  .figsvg .hid{stroke-dasharray:5 4; fill:none;}
  .figsvg .tick{stroke:var(--ink); stroke-width:1.4; fill:none;}
  .figsvg .shd{fill:var(--accent-text); fill-opacity:.55;}
  .figsvg .cell{fill:var(--card); stroke:var(--ink); stroke-width:1.1;}
  .figsvg .dr{fill:var(--danger);} .figsvg .dw{fill:var(--card); stroke:var(--ink); stroke-width:1.2;}
  .figsvg .dotfill{fill:var(--danger);}
  .tt{border-collapse:collapse; font-size:13.5px; margin:4px auto; font-variant-numeric:tabular-nums;} .tt th,.tt td{border:1px solid var(--rule); padding:4px 9px; text-align:left;} .tt th{background:var(--paper-2); font-weight:700;} .ttw{overflow-x:auto; max-width:100%;}
  .fq{display:inline-flex; flex-direction:column; vertical-align:middle; text-align:center; font-size:.82em; line-height:1.12; margin:0 2px;}
  .fq>span:first-child{border-bottom:1.5px solid currentColor; padding:0 2px;}
  .fq>span:last-child{padding:0 2px;}
  .mx{white-space:nowrap;}
  .blank-input.fr{width:110px;}
  @media (prefers-reduced-motion:reduce){ *{transition:none !important;} }
.datline{display:block;margin-top:8px;padding:8px 10px;border-radius:8px;background:var(--paper-2);font:500 14px/1.7 'IBM Plex Mono',monospace;word-spacing:2px;overflow-wrap:anywhere;}

  .theory{display:flex;flex-direction:column;gap:16px;padding-bottom:40px;}
  .hub{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .hub{grid-template-columns:repeat(3,1fr);} }
  .hub-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:16px;display:flex;flex-direction:column;gap:8px;}
  .hub-card h3{font-family:'Fraunces',serif;font-size:18px;margin:0;color:var(--accent-text);}
  .hub-card p{margin:0;font-size:14px;color:var(--ink-soft);line-height:1.5;}
  .hub-btns{display:flex;flex-wrap:wrap;gap:8px;margin-top:auto;}
  .hub-btn{min-height:40px;border:1.5px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:10px;padding:8px 12px;font:600 14px 'Source Sans 3',sans-serif;cursor:pointer;text-align:left;}
  .hub-btn:hover{border-color:var(--gold);}
  .hub-btn.primary{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .note{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:18px;scroll-margin-top:120px;}
  .note h2{font-family:'Fraunces',serif;font-size:22px;margin:0 0 4px;color:var(--ink);}
  .note .lt{font-size:13.5px;color:var(--ink-soft);margin:0 0 12px;}
  .note .lt b{color:var(--accent-text);}
  .note h4{font:700 15px 'Source Sans 3',sans-serif;margin:16px 0 6px;color:var(--accent-text);}
  .note p,.note li{font-size:15.5px;line-height:1.6;}
  .note ul{padding-left:20px;margin:6px 0;}
  .keybox{background:var(--gold-soft);border-left:4px solid var(--gold);border-radius:8px;padding:10px 12px;margin:10px 0;font-size:15px;line-height:1.6;}
  .keybox b{color:var(--ink);}
  .ex{background:var(--paper-2);border-radius:10px;padding:12px;margin:10px 0;}
  .ex .exh{font-family:'Fraunces',serif;font-weight:700;color:var(--accent-text);margin-bottom:4px;}
  .ex .exl{font-size:15px;line-height:1.7;}
  .ttab{width:100%;border-collapse:collapse;font-size:14.5px;margin:8px 0;}
  .ttab th,.ttab td{border:1px solid var(--rule);padding:7px 8px;text-align:left;vertical-align:top;}
  .ttab th{background:var(--paper-2);}
  .tscroll{overflow-x:auto;}
  .mono{font-family:'IBM Plex Mono',monospace;font-size:.92em;}
  @media (max-width:480px){ .ttab{font-size:13.5px;} .ttab th,.ttab td{padding:6px;} }
  .note .figsvg{max-width:100%;height:auto;display:block;margin:8px auto;}


  .rep-top{display:flex;flex-wrap:wrap;gap:18px;align-items:center;justify-content:center;margin-top:8px;}
  .rep-legend{flex:1;min-width:220px;display:flex;flex-direction:column;gap:8px;}
  .rep-cap{font:700 13px 'Source Sans 3',sans-serif;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.05em;}
  .rep-li{display:flex;align-items:center;gap:6px;font-size:15px;}
  .rep-n{margin-left:auto;white-space:nowrap;padding-left:8px;font-family:'IBM Plex Mono',monospace;font-weight:600;}
  .sw{display:inline-block;width:12px;height:12px;border-radius:3px;flex:none;}
  .rep-grid{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .rep-grid{grid-template-columns:1fr 1fr;} }
  .rep-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:14px;display:flex;flex-direction:column;gap:10px;}
  .rep-h{display:flex;align-items:center;gap:8px;font:700 16px 'Source Sans 3',sans-serif;}
  .crit{display:inline-grid;place-items:center;width:28px;height:28px;border-radius:50%;color:var(--card);font:700 15px Fraunces,serif;flex:none;}
  .rep-row{display:flex;gap:14px;align-items:center;}
  .rep-stats{display:flex;flex-direction:column;gap:5px;font-size:14.5px;}
  .rep-stats div{display:flex;align-items:center;gap:6px;}
  .rep-lvl{margin-top:4px;color:var(--accent-text);} .rep-lvl span{color:var(--ink-soft);font-size:13px;}
  .rep-note{font-size:13px;color:var(--ink-soft);}


  .skip-chips{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin:12px 0;}
  .skip-chips .chip{min-width:48px;min-height:40px;cursor:pointer;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--retry-text);border-radius:10px;font:600 14px 'IBM Plex Mono',monospace;}
  .skip-btns{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-top:12px;}

</style>
</head>
<body>
<header class="brand">
  <div class="brand-row">
    <div class="crest">BM</div>
    <div>
      <div class="brand-name">Brain &amp; Mind Academy</div>
      <div class="series-name">Sopaan <span style="font-weight:400;font-size:14px;color:#CFD7EA;">Practice Series</span></div>
    </div>
  </div>
  <div class="chapter-eyebrow">MYP Mathematics 2 · Unit 4</div>
  <div class="chapter-title">Algebraic expressions and equations</div>
  <div class="chapter-sub">Theory Notes · Objective-wise Practice · Criterion Tests A–D</div><div class="chapter-credit">Follows the unit structure of MYP Mathematics 2 (Oxford), Unit 4</div>
  <div class="chapter-progress">
    <div class="cp-track"><div class="cp-fill" id="cpFill"></div></div>
    <div class="cp-label" id="cpLabel">0% complete</div>
  </div>
  <div class="who-row"><button class="mode-pill" id="modePill" hidden>Choose a mode</button><span class="who" id="whoBar" hidden></span></div>
</header>

<nav class="tabbar"><div class="tabbar-inner" id="tabbar"></div></nav>
<div class="sec-sub" id="secSub"></div><div class="slide-progress"><div class="sp-track"><div class="sp-fill" id="spFill"></div></div><div class="sp-label" id="spLabel">Question 1 of 49</div></div>
<div class="wrap" id="wrap"></div>
<footer class="brandfoot">Brain &amp; Mind Academy · Sopaan Practice Series · MYP Mathematics 2 · Unit 4<br>Unit objectives and structure follow <i>MYP Mathematics 2: A concept-based approach</i> (Oxford University Press), Unit 4. Theory notes, questions, tests and worked solutions are written by Brain &amp; Mind Academy.</footer>

<div class="navbar"><div class="navbar-inner" id="navbarInner"></div></div>
<button class="fab" id="paletteFab"><span>Questions</span><span class="fab-badge" id="fabBadge">0/49</span></button>

<div class="overlay" id="overlay">
  <div class="palette" role="dialog" aria-label="Question palette">
    <div class="palette-head"><h2 id="paletteTitle">Question palette</h2><button class="palette-close" id="paletteClose">&times;</button></div>
    <div class="palette-legend">
      <span><i class="dot current"></i>Current</span><span><i class="dot correct"></i>Correct</span>
      <span><i class="dot revealed"></i>Revealed</span><span><i class="dot skipped"></i>Skipped</span>
      <span><i class="dot locked"></i>Locked</span>
    </div>
    <div class="chip-grid" id="paletteBody"></div>
  </div>
</div>
<div class="toast" id="toast"></div>

<script>
(function(){
"use strict";

/* ================= audio ================= */
var audioCtx=null;
function ensureAudio(){ if(!audioCtx){ try{ audioCtx=new (window.AudioContext||window.webkitAudioContext)(); }catch(e){} } return audioCtx; }
function playTone(freqs,dur,type){
  var ctx=ensureAudio(); if(!ctx) return;
  try{
    var t0=ctx.currentTime;
    freqs.forEach(function(f,i){
      var o=ctx.createOscillator(), g=ctx.createGain();
      o.type=type||'sine'; o.frequency.value=f;
      var start=t0+i*dur;
      g.gain.setValueAtTime(0.0001,start);
      g.gain.exponentialRampToValueAtTime(0.16,start+0.02);
      g.gain.exponentialRampToValueAtTime(0.0001,start+dur);
      o.connect(g); g.connect(ctx.destination);
      o.start(start); o.stop(start+dur+0.02);
    });
  }catch(e){}
}
function playSuccess(){ playTone([523.25,659.25,783.99],0.11,'sine'); }
function playWrong(){ playTone([220,185],0.14,'square'); }
function playReveal(){ playTone([300,220],0.16,'triangle'); }

/* ================= helpers ================= */
function norm(s){
  return String(s===undefined||s===null?'':s).trim().toLowerCase().replace(/\s+/g,'')
    .replace(/[×∗*·]/g,'x').replace(/÷/g,'/').replace(/–|—|−/g,'-')
    .replace(/[²]/g,'^2').replace(/[³]/g,'^3').replace(/[⁴]/g,'^4').replace(/[⁵]/g,'^5')
    .replace(/[⁶]/g,'^6').replace(/[⁷]/g,'^7').replace(/[⁸]/g,'^8').replace(/[⁹]/g,'^9')
    .replace(/\^/g,'');
}
function parseNum(s){
  if(s===undefined||s===null) return null;
  var t=String(s).trim().replace(/,/g,'').replace(/[−–—]/g,'-').replace(/\s+/g,''); if(t==='') return null;
  var neg=false; if(t[0]==='-'){neg=true;t=t.slice(1);}
  var m=t.match(/^(\d+)\/(\d+)$/);
  if(m){ var v=parseInt(m[1],10)/parseInt(m[2],10); return neg?-v:v; }
  if(/^\d+(\.\d+)?$/.test(t)){ var v2=parseFloat(t); return neg?-v2:v2; }
  return null;
}
/* ---- expression checker: compares answers like (P-2w)/2 and P/2-w at random values ---- */
function exprPrep(s){
  return String(s).toLowerCase().replace(/\s+/g,'').replace(/^[a-z]\(x\)=/i,'').replace(/^y=/i,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/⁴/g,'^4').replace(/⁵/g,'^5').replace(/⁶/g,'^6').replace(/⁷/g,'^7').replace(/⁸/g,'^8').replace(/⁹/g,'^9').replace(/π/g,'#').replace(/pi/gi,'#').replace(/½/g,'(1/2)');
}
function exprCompile(src){
  var s=exprPrep(src), i=0, toks=[], absDepth=0;
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length && /[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(/[a-zA-Z#]/.test(ch)){ toks.push({k:'v',v:ch}); i++; continue; }
    if(ch==='|'){ var pv=toks[toks.length-1]; var opn=(absDepth===0)||!pv||('+-*/^(['.indexOf(pv.k)>=0); if(opn){ absDepth++; toks.push({k:'['}); } else { absDepth--; toks.push({k:']'}); } i++; continue; }
    if('+-*/^()'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  var out=[];
  for(var t=0;t<toks.length;t++){
    var a=toks[t], b=out[out.length-1];
    if(b && (b.k==='n'||b.k==='v'||b.k===')'||b.k===']') && (a.k==='n'||a.k==='v'||a.k==='('||a.k==='[')) out.push({k:'&'});
    out.push(a);
  }
  var p=0;
  function peek(){ return out[p]; }
  function parseE(){ var n=parseT(); while(peek() && (peek().k==='+'||peek().k==='-')){ var o=out[p++].k, r=parseT(); n=(function(l,r,o){return function(e){ return o==='+'?l(e)+r(e):l(e)-r(e); };})(n,r,o); } return n; }
  function parseI(){ var n=parseU(); while(peek() && peek().k==='&'){ p++; var r=parseP(); n=(function(l,r){return function(e){ return l(e)*r(e); };})(n,r); } return n; }
  function parseT(){ var n=parseI(); while(peek() && (peek().k==='*'||peek().k==='/')){ var o=out[p++].k, r=parseI(); n=(function(l,r,o){return function(e){ return o==='*'?l(e)*r(e):l(e)/r(e); };})(n,r,o); } return n; }
  function parseU(){ if(peek() && peek().k==='-'){ p++; var u=parseU(); return function(e){ return -u(e); }; } if(peek() && peek().k==='+'){ p++; return parseU(); } return parseP(); }
  function parseP(){ var b=parseA(); if(peek() && peek().k==='^'){ p++; var x=parseU(); return function(e){ return Math.pow(b(e),x(e)); }; } return b; }
  function parseA(){
    var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){ return t.v; };
    if(t.k==='v') return t.v==='#' ? function(){ return Math.PI; } : function(e){ return e[t.v]; };
    if(t.k==='('){ var n=parseE(); if(!peek()||peek().k!==')') throw 0; p++; return n; }
    if(t.k==='['){ var m=parseE(); if(!peek()||peek().k!==']') throw 0; p++; return function(e){ return Math.abs(m(e)); }; }
    throw 0;
  }
  try{ var f=parseE(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function exprEqual(input,answer){
  var f=exprCompile(input), g=exprCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<8;trial++){
    var env={}; 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=1.3+Math.random()*4.1; });
    var x=f(env), y=g(env);
    if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-7*Math.max(1,Math.abs(x),Math.abs(y))) return false;
    hits++;
  }
  return hits>=3;
}
function wordsNorm(s){ return String(s||'').toLowerCase().replace(/\band\b/g,' ').replace(/[^a-z]/g,''); }
function listNorm(s){ return (String(s||'').replace(/[−–—]/g,'-').replace(/(\d) (?=\d{3}\b)/g,'$1').match(/-?\d+(\.\d+)?/g)||[]).join(','); }
function powNorm(s){ return String(s||'').toLowerCase().replace(/\s+/g,'').replace(/[×∗*·.]/g,'x').replace(/[⁰¹²³⁴⁵⁶⁷⁸⁹]+/g,function(m){ return '^'+m.split('').map(function(c){ return '⁰¹²³⁴⁵⁶⁷⁸⁹'.indexOf(c); }).join(''); }).replace(/\^1(?!\d)/g,''); }
function fr(s){ return String(s).replace(/\{(\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>').replace(/\{(\d+)\/(\d+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); }
function gcdI(a,b){ a=Math.abs(a); b=Math.abs(b); while(b){ var t=a%b; a=b; b=t; } return a; }
function fracParse(s){ s=String(s===undefined||s===null?'':s).trim().replace(/[\u2044\u2215\u00f7]/g,'/').replace(/\s+/g,' ').replace(/\s*\/\s*/g,'/'); var m;
  if((m=s.match(/^(-?\d+)$/))) return {v:+m[1],form:'int',n:+m[1],d:1};
  if((m=s.match(/^(-?\d+)\/(\d+)$/))){ if(+m[2]===0) return null; return {v:m[1]/m[2],form:'frac',n:+m[1],d:+m[2]}; }
  if((m=s.match(/^(\d+)(?: |\+|-)(\d+)\/(\d+)$/))){ if(+m[3]===0) return null; return {v:+m[1]+m[2]/m[3],form:'mixed',w:+m[1],n:+m[2],d:+m[3]}; }
  if((m=s.match(/^-?\d*\.\d+$/))) return {v:parseFloat(s),form:'dec'};
  return null; }
function fracOK(mode,input,answer){
  if(mode==='flist'){ var A=String(input).split(/[,;]/).map(function(x){return x.trim();}).filter(Boolean), K=String(answer).split(/[,;]/).map(function(x){return x.trim();});
    if(A.length!==K.length) return false; return A.every(function(x,i){ var a=fracParse(x), k=fracParse(K[i]); return a&&k&&Math.abs(a.v-k.v)<1e-9; }); }
  var a=fracParse(input), k=fracParse(answer); if(!a||!k) return false;
  var same=Math.abs(a.v-k.v)<1e-9; if(!same) return false;
  if(mode==='fv') return true;
  if(mode==='dec') return a.form==='dec'||a.form==='int';
  if(mode==='fe') return (a.form==='frac'&&k.form==='frac'&&a.n===k.n&&a.d===k.d)||(a.form==='int'&&k.form==='int');
  if(mode==='fi') return a.form==='frac'||(a.form==='int'&&k.form==='int');
  if(mode==='fl') return a.form==='int'||(a.form==='frac'&&gcdI(a.n,a.d)===1)||(a.form==='mixed'&&a.n<a.d&&gcdI(a.n,a.d)===1);
  if(mode==='fm') return a.form==='int'||(a.form==='mixed'&&a.n>0&&a.n<a.d&&gcdI(a.n,a.d)===1);
  return false; }
function answerMatches(input,answer,accept,expr){
  if(expr==='dec'||expr==='fv'||expr==='fe'||expr==='fl'||expr==='fm'||expr==='fi'||expr==='flist'){ if(input===undefined||input===null||String(input).trim()==='') return false; return fracOK(expr,input,answer); }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  if(expr==='words'){ return [answer].concat(accept||[]).some(function(a){ if(/\d/.test(a)) return norm(a)===norm(input); var w=wordsNorm(a); return w!=='' && w===wordsNorm(input); }); }
  if(expr==='list'){ return [answer].concat(accept||[]).some(function(a){ return listNorm(a)===listNorm(input); }); }
  if(expr==='pow'){ return [answer].concat(accept||[]).some(function(a){ return powNorm(a)===powNorm(input); }); }
  if(expr==='time'){ var tn=function(x){ var t=String(x).toLowerCase().replace(/[\s.]/g,'').replace(/[:h]/g,''); if(/^\d{3}(am|pm)?$/.test(t)) t='0'+t; return t; }; return [answer].concat(accept||[]).some(function(a){ return tn(a)===tn(input); }); }
  if(expr==='glist'){ var gn=function(x){ return String(x).toUpperCase().split(/[\s,;]+/).filter(Boolean).sort().join(','); }; return [answer].concat(accept||[]).some(function(a){ return gn(a)===gn(input); }); }
  if(expr==='coord'){ var cn=function(x){ return String(x).replace(/[\u2212\u2013\u2014]/g,'-').replace(/[\s()\[\]]/g,''); }; return [answer].concat(accept||[]).some(function(a){ return cn(a)===cn(input); }); }
  if(expr==='dlist'){ var dn=function(x){ return (String(x).replace(/[−–—]/g,'-').match(/-?\d*\.?\d+/g)||[]).map(Number).join(','); }; return [answer].concat(accept||[]).some(function(a){ return dn(a)===dn(input); }); }
  if(expr==='set'){ var sn=function(x){ return (String(x).match(/-?\d+/g)||[]).map(Number).sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return sn(a)===sn(input); }); }
  if(expr==='primes'){ var pn=function(x){ var t=powNorm(x).replace(/[^0-9x^]/g,''); var out=[]; t.split('x').forEach(function(tok){ if(!tok) return; var m=tok.split('^'); var b=+m[0], e=m[1]?+m[1]:1; for(var i=0;i<e;i++) out.push(b); }); return out.sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return pn(a)===pn(input); }); }
  if(expr==='angle'){ var an=function(x){ return String(x).toUpperCase().replace(/[^A-Z]/g,''); }; var k=an(answer), v=an(input); return v===k || v===k.split('').reverse().join(''); }
  if(expr==='trans'){ var tv=function(x){ var s=String(x).toLowerCase().replace(/[−–—]/g,'-').replace(/\b(units?|squares?|and|then|steps?|to|the|a)\b/g,' ').replace(/[,;.]/g,' '); var re=/(\d+)\s*(right|left|up|down|r|l|u|d)\b/g, m, dx=0, dy=0, n=0; while((m=re.exec(s))){ var v=+m[1], d=m[2][0]; if(d==='r')dx+=v; else if(d==='l')dx-=v; else if(d==='u')dy+=v; else dy-=v; n++; } if(!n||s.replace(re,'').replace(/\s+/g,'')!=='') return null; return dx+','+dy; }; var ti=tv(input); return ti!==null && [answer].concat(accept||[]).some(function(a){ return tv(a)===ti; }); }
  if(expr==='rot'){ var rv=function(x){ var s=String(x).toLowerCase().replace(/quarter[\s-]*turn/g,'90').replace(/half[\s-]*turn/g,'180').replace(/three[\s-]*quarter[\s-]*turn/g,'270'); var m=s.match(/\b(90|180|270)\b/); if(!m) return null; var a=+m[1]; if(a===180) return '180'; var dir=/anti|counter|acw|ccw/.test(s)?-1:(/clockwise|\bcw\b/.test(s)?1:0); if(!dir) return null; return String(((a*dir)%360+360)%360); }; var ri=rv(input); return ri!==null && ri===rv(answer); }
  if(expr==='expanded'){ var f=function(x){ return String(x).replace(/\s+/g,'').replace(/,/g,''); }; return [answer].concat(accept||[]).some(function(a){ return f(a)===f(input); }); }
  if(expr===true && input!==undefined && input!==null && String(input).trim()!==''){
    if(exprEqual(input,answer)) return true;
    var alt=String(input).replace(/\/\s*(\d+(?:\.\d+)?)\s*([a-zA-Z(])/g,'/$1*$2'); if(alt!==String(input) && exprEqual(alt,answer)) return true;
    return (accept||[]).some(function(a){ return exprEqual(input,a); });
  }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  var n1=parseNum(input), n2=parseNum(answer);
  if(n1!==null && n2!==null){ if(Math.abs(n1-n2)<1e-3) return true; return (accept||[]).some(function(a){ var n3=parseNum(a); return n3!==null && Math.abs(n1-n3)<1e-3; }); }
  var cands=[answer].concat(accept||[]); var ni=norm(input);
  for(var i=0;i<cands.length;i++){ if(norm(cands[i])===ni) return true; }
  return false;
}
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;'); }

/* ================= DATA ================= */
var AR_OPTIONS = ["Both A and R are true, and R is the correct explanation of A","Both A and R are true, but R is NOT the correct explanation of A","A is true but R is false","A is false but R is true"];
var THEORY = "<div class=\"hub\"><div class=\"hub-card\"><h3>📖 Theory notes</h3><p>Explained notes for each part of the unit, with rules, diagrams and worked examples.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-jump=\"n41\">4.1 notes</button><button class=\"hub-btn\" data-jump=\"n42\">4.2 notes</button><button class=\"hub-btn\" data-jump=\"n43\">4.3 notes</button><button class=\"hub-btn\" data-jump=\"n44\">4.4 notes</button><button class=\"hub-btn\" data-jump=\"n45\">4.5 notes</button><button class=\"hub-btn\" data-jump=\"n46\">4.6 notes</button></div></div><div class=\"hub-card\"><h3>🎯 Objective-wise practice</h3><p>One practice sheet for each unit objective: multiple-choice questions first, then step-by-step fill-in-the-blanks.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s1\">4.1 · Classifying polynomials</button><button class=\"hub-btn\" data-go=\"s2\">4.2 · Simplifying and expanding</button><button class=\"hub-btn\" data-go=\"s3\">4.3 · Writing expressions and number tricks</button><button class=\"hub-btn\" data-go=\"s4\">4.4 · Solving equations</button><button class=\"hub-btn\" data-go=\"s5\">4.5 · Writing equations and inverse functions</button><button class=\"hub-btn\" data-go=\"s6\">4.6 · Inequalities</button></div></div><div class=\"hub-card\"><h3>📝 Chapter test</h3><p>Four tests, one for each MYP criterion. Take them in Quiz mode, then open the report to see your results as pie charts.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s7\">Test A · Knowing and understanding</button><button class=\"hub-btn\" data-go=\"s8\">Test B · Investigating patterns</button><button class=\"hub-btn\" data-go=\"s9\">Test C · Communicating</button><button class=\"hub-btn\" data-go=\"s10\">Test D · Applying mathematics in real-life contexts</button><button class=\"hub-btn primary\" data-go=\"report\">📊 View my report</button></div></div></div><section class=\"note\" id=\"nintro\"><h2>About this unit</h2><p><b>Key concept:</b> Form &nbsp;·&nbsp; <b>Related concepts:</b> Simplification, Equivalence &nbsp;·&nbsp; <b>Global context:</b> Scientific and technical innovation.</p><p>Many “mind-reading” tricks, calendar puzzles and secret codes work because of simple algebra. Writing a situation as an expression, simplifying it to an equivalent form, and solving equations and inequalities lets you explain every trick, and invent your own.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Test</th><th>MYP criterion</th><th>What it checks</th></tr><tr><td>Test A</td><td>Knowing and understanding</td><td>Classifying, simplifying, expanding and solving correctly.</td></tr><tr><td>Test B</td><td>Investigating patterns</td><td>Testing number tricks and patterns, then stating and proving a general rule with algebra.</td></tr><tr><td>Test C</td><td>Communicating</td><td>Correct vocabulary and notation, spotting errors, and clear explanations.</td></tr><tr><td>Test D</td><td>Applying mathematics in real-life contexts</td><td>Writing and solving equations and inequalities for real situations, and judging answers.</td></tr></table></div></section><section class=\"note\" id=\"n41\"><h2>4.1 Classifying polynomials</h2><p class=\"lt\"><b>Objective:</b> Define and classify polynomials by their number of terms and their degree, and write them in standard form.</p><h4>Terms, coefficients and constants</h4><p>An <b>algebraic expression</b> is made of numbers, variables (letters) and operations. A <b>term</b> is a single number, a single variable, or numbers and variables multiplied together, such as <span class=\"mono\">7</span>, <span class=\"mono\">−4x</span> or <span class=\"mono\">3a²b</span>. Terms are separated by + and − signs.</p><ul><li>The <b>coefficient</b> is the number multiplying the variables: in −4x it is −4; in a²b it is 1.</li><li>A <b>constant term</b> has no variable, e.g. the 9 in 2x + 9.</li></ul><h4>Naming by number of terms</h4><p>A <b>polynomial</b> is an expression with one or more terms where every variable has a whole-number exponent (0, 1, 2, …) and no variable is in a denominator or under a root.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Number of terms</th><th>Name</th><th>Example</th></tr><tr><td>1</td><td>monomial</td><td class=\"mono\">−8pq</td></tr><tr><td>2</td><td>binomial</td><td class=\"mono\">5x − 3y</td></tr><tr><td>3</td><td>trinomial</td><td class=\"mono\">m² + 4m − 1</td></tr><tr><td>4 or more</td><td>polynomial</td><td class=\"mono\">x³ − 2x² + x − 6</td></tr></table></div><h4>Degree</h4><p>The <b>degree of a term</b> is the sum of the exponents of its variables: 3a²b has degree 2 + 1 = 3; a constant such as 7 has degree 0. The <b>degree of a polynomial</b> is the highest degree of any of its terms.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Degree</th><th>Name</th><th>Example</th></tr><tr><td>0</td><td>constant</td><td class=\"mono\">−5</td></tr><tr><td>1</td><td>linear</td><td class=\"mono\">4x + 1</td></tr><tr><td>2</td><td>quadratic</td><td class=\"mono\">x² − 9</td></tr><tr><td>3</td><td>cubic</td><td class=\"mono\">2y³ + y</td></tr><tr><td>4</td><td>quartic</td><td class=\"mono\">k⁴ − 3k</td></tr><tr><td>5</td><td>quintic</td><td class=\"mono\">n⁵ + 1</td></tr></table></div><div class=\"keybox\"><b>Degree is not the biggest exponent you can see.</b> In x²y³ + x⁴ the first term has degree 2 + 3 = 5, so the polynomial has degree 5, not 4. Add the exponents within each term first.</div><h4>Standard form</h4><p>A polynomial in one variable is in <b>standard form</b> when its terms are written in descending order of degree, with the constant last.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Classify</div><div class=\"exl\">Classify 5a³b − 2ab + 7.<br>Three terms, so it is a <b>trinomial</b>.<br>Degrees of the terms: 3 + 1 = 4, 1 + 1 = 2 and 0. The polynomial has <b>degree 4</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Standard form</div><div class=\"exl\">Write 4 − 3y + 2y³ − y² in standard form and name it.<br>Order by degree: <b>2y³ − y² − 3y + 4</b>.<br>Highest degree 3 with four terms: a <b>cubic polynomial</b>. The leading coefficient is 2.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Not a polynomial</div><div class=\"exl\">Is <span class=\"fq\"><span>3</span><span>x</span></span> + 1 a polynomial?<br><span class=\"fq\"><span>3</span><span>x</span></span> = 3x<sup>−1</sup>: the variable is in the denominator (a negative exponent).<br>So it is <b>not</b> a polynomial. (But <span class=\"fq\"><span>x</span><span>3</span></span> + 1 is, because it equals ⅓x + 1.)</div></div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s1\">Practise 4.1 →</button></div></section><section class=\"note\" id=\"n42\"><h2>4.2 Simplifying and expanding</h2><p class=\"lt\"><b>Objective:</b> Identify like terms, simplify algebraic expressions and expand brackets using the distributive property.</p><h4>Like terms</h4><p><b>Like terms</b> have exactly the same variables raised to the same exponents; only the coefficients may differ.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Like terms</th><th>Not like terms</th><th>Why not?</th></tr><tr><td class=\"mono\">6x and −x</td><td class=\"mono\">6x and 6y</td><td>different variables</td></tr><tr><td class=\"mono\">2a²b and 9a²b</td><td class=\"mono\">2a²b and 2ab²</td><td>exponents on different letters</td></tr><tr><td class=\"mono\">5mn and −3nm</td><td class=\"mono\">4k and 4k²</td><td>different exponents</td></tr><tr><td class=\"mono\">8 and −12</td><td class=\"mono\">8 and 8t</td><td>one has no variable</td></tr></table></div><p>To <b>simplify</b>, add or subtract the coefficients of like terms. The variable part does not change: 3x² + 5x² = 8x², never 8x⁴.</p><div class=\"keybox\"><b>Keep the sign with the term.</b> In 7 − 4n + 2n, the term is −4n, so −4n + 2n = −2n and the answer is 7 − 2n.</div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Two variables</div><div class=\"exl\">Simplify 4p + 3q − p + 5q − 2.<br>p terms: 4p − p = 3p. q terms: 3q + 5q = 8q. The constant −2 has no partner.<br>Answer: <b>3p + 8q − 2</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Powers</div><div class=\"exl\">Simplify 2x² + 5x − 3x² + x + 4.<br>x² terms: 2x² − 3x² = −x². x terms: 5x + x = 6x.<br>Answer in standard form: <b>−x² + 6x + 4</b>.</div></div><h4>Expanding brackets: the distributive property</h4><p>Multiply <b>every</b> term inside the bracket by the term outside: a(b + c) = ab + ac. An area model shows why: a rectangle of width 4 and length 3x + 7 splits into two parts.</p><svg class=\"figsvg\" viewBox=\"0 0 300 120\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"al\" x=\"30.0\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><rect x=\"44.0\" y=\"26\" width=\"146.4\" height=\"70\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.4\"/><text class=\"al\" x=\"117.2\" y=\"16.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3x</text><text class=\"lb\" x=\"117.2\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4 × 3x = 12x</text><rect x=\"190.4\" y=\"26\" width=\"97.6\" height=\"70\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.4\"/><text class=\"al\" x=\"239.2\" y=\"16.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><text class=\"lb\" x=\"239.2\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4 × 7 = 28</text></svg><p>So 4(3x + 7) = 12x + 28.</p><div class=\"keybox\"><b>A negative outside changes every sign inside.</b> −3(y − 4) = −3y + 12, because −3 × −4 = +12. A lone minus sign in front of a bracket means −1: −(c + 5) = −c − 5.</div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Expand and simplify</div><div class=\"exl\">Simplify 5(2y − 3) − 3(y − 4).<br>Expand: 10y − 15 − 3y + 12.<br>Collect like terms: <b>7y − 3</b>.</div></div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s2\">Practise 4.2 →</button></div></section><section class=\"note\" id=\"n43\"><h2>4.3 Writing expressions and number tricks</h2><p class=\"lt\"><b>Objective:</b> Write algebraic expressions from words and use them to justify number tricks and puzzles.</p><h4>From words to algebra</h4><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Words</th><th>Expression</th></tr><tr><td>a number increased by 5</td><td class=\"mono\">n + 5</td></tr><tr><td>7 less than a number</td><td class=\"mono\">n − 7</td></tr><tr><td>a number subtracted from 7</td><td class=\"mono\">7 − n</td></tr><tr><td>twice a number, plus 3</td><td class=\"mono\">2n + 3</td></tr><tr><td>twice (a number plus 3)</td><td class=\"mono\">2(n + 3)</td></tr><tr><td>half of a number</td><td class=\"mono\">n/2</td></tr><tr><td>three consecutive integers</td><td class=\"mono\">n, n + 1, n + 2</td></tr><tr><td>any even number / any odd number</td><td class=\"mono\">2n / 2n + 1</td></tr><tr><td>a two-digit number with digits a and b</td><td class=\"mono\">10a + b</td></tr></table></div><div class=\"keybox\"><b>“Less than” reverses the order.</b> “7 less than n” is n − 7, but “n less than 7” is 7 − n. Use brackets when a whole expression is multiplied or divided.</div><h4>Why number tricks work</h4><p>A “think of a number” trick always gives the same answer because, once you write the steps with a variable and simplify, the variable cancels out.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Justify a trick</div><div class=\"exl\">Think of a number, add 4, multiply by 3, subtract 6, divide by 3, then subtract the number you first thought of.<br>n → n + 4 → 3(n + 4) = 3n + 12 → 3n + 6 → n + 2 → n + 2 − n = <b>2</b>.<br>The answer is always 2, whatever number is chosen.</div></div><h4>Calendar puzzles</h4><p>On a calendar, the date to the right of n is n + 1 and the date directly below is n + 7.</p><div class=\"tscroll\"><table class=\"ttab\" style=\"width:auto\"><tr><td class=\"mono\">n</td><td class=\"mono\">n + 1</td></tr><tr><td class=\"mono\">n + 7</td><td class=\"mono\">n + 8</td></tr></table></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · A 2 × 2 block</div><div class=\"exl\">Show that the four dates in any 2 × 2 block add up to 4 times the smallest date, plus 16.<br>n + (n + 1) + (n + 7) + (n + 8) = <b>4n + 16</b>.<br>So if a friend says the sum is 76, then 4n + 16 = 76, n = 15: the dates are 15, 16, 22, 23.</div></div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s3\">Practise 4.3 →</button></div></section><section class=\"note\" id=\"n44\"><h2>4.4 Solving equations</h2><p class=\"lt\"><b>Objective:</b> Solve equations, including equations with brackets, fractions and the variable on both sides.</p><p>An <b>equation</b> says that two expressions are equal. Think of a balance: whatever you do to one side, you must do to the other so it stays level. Use <b>inverse (opposite) operations</b> to get the variable on its own.</p><svg class=\"figsvg\" viewBox=\"0 0 300 146\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"150.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Take 2 from both sides, then divide by 3</text><path d=\"M150.0,68 L132.0,132 L168.0,132 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.4\"/><line x1=\"30.0\" y1=\"68\" x2=\"270.0\" y2=\"68\" style=\"stroke:var(--ink);stroke-width:3;stroke-linecap:round\"/><line x1=\"60.0\" y1=\"68\" x2=\"60.0\" y2=\"60\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"10.0\" y=\"28\" width=\"100\" height=\"32\" rx=\"6\" style=\"fill:var(--gold-soft);stroke:var(--gold);stroke-width:1.4\"/><text class=\"lb\" x=\"60.0\" y=\"44.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3x + 2</text><line x1=\"240.0\" y1=\"68\" x2=\"240.0\" y2=\"60\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"190.0\" y=\"28\" width=\"100\" height=\"32\" rx=\"6\" style=\"fill:var(--gold-soft);stroke:var(--gold);stroke-width:1.4\"/><text class=\"lb\" x=\"240.0\" y=\"44.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">14</text></svg><div class=\"tscroll\"><table class=\"ttab\"><tr><th>To undo</th><th>do this to both sides</th></tr><tr><td>+ 5</td><td>− 5</td></tr><tr><td>− 5</td><td>+ 5</td></tr><tr><td>× 5</td><td>÷ 5</td></tr><tr><td>÷ 5</td><td>× 5</td></tr></table></div><h4>A method for any linear equation</h4><ul><li><b>Brackets:</b> expand them first.</li><li><b>Fractions:</b> multiply both sides by the denominator.</li><li><b>Variable on both sides:</b> subtract the smaller variable term from both sides.</li><li><b>Undo</b> addition/subtraction, then multiplication/division.</li><li><b>Check</b> by substituting your answer into the original equation.</li></ul><div class=\"ex\"><div class=\"exh\">Worked example 1 · Two-step</div><div class=\"exl\">Solve 5x − 8 = 17.<br>Add 8: 5x = 25. Divide by 5: <b>x = 5</b>.<br>Check: 5 × 5 − 8 = 17 ✓</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Both sides</div><div class=\"exl\">Solve 7a + 3 = 3a + 23.<br>Subtract 3a: 4a + 3 = 23. Subtract 3: 4a = 20.<br><b>a = 5</b>. Check: 38 = 38 ✓</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Brackets</div><div class=\"exl\">Solve 4(b − 2) = 2(b + 5).<br>Expand: 4b − 8 = 2b + 10. Subtract 2b: 2b − 8 = 10.<br>Add 8: 2b = 18, so <b>b = 9</b>. Check: 4 × 7 = 28 and 2 × 14 = 28 ✓</div></div><div class=\"ex\"><div class=\"exh\">Worked example 4 · A fraction</div><div class=\"exl\">Solve <span class=\"fq\"><span>y</span><span>3</span></span> + 4 = 10.<br>Subtract 4: <span class=\"fq\"><span>y</span><span>3</span></span> = 6.<br>Multiply by 3: <b>y = 18</b>.</div></div><div class=\"keybox\"><b>Do the same to the whole side.</b> To clear the fraction in <span class=\"fq\"><span>x + 1</span><span>2</span></span> = 5, multiply the whole of each side by 2: x + 1 = 10. Also watch negatives: −2x = 8 gives x = −4.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s4\">Practise 4.4 →</button></div></section><section class=\"note\" id=\"n45\"><h2>4.5 Writing equations and inverse functions</h2><p class=\"lt\"><b>Objective:</b> Write equations to solve problems, and use inverse functions to encode and decode messages.</p><h4>Writing an equation for a problem</h4><ul><li><b>Define</b> a variable for the unknown (“let n be …”).</li><li>Write the other quantities in terms of it.</li><li>Write an <b>equation</b> from the fact you are given, and solve it.</li><li><b>Check</b> and answer the question in words.</li></ul><div class=\"ex\"><div class=\"exh\">Worked example 1 · Consecutive even numbers</div><div class=\"exl\">Three consecutive even numbers add up to 78. Find them.<br>Let them be n, n + 2 and n + 4. Then 3n + 6 = 78, so 3n = 72 and n = 24.<br>The numbers are <b>24, 26 and 28</b> (24 + 26 + 28 = 78 ✓).</div></div><h4>Inverse functions</h4><p>A function such as y = 3x + 5 turns an input x into an output y. The <b>inverse function</b> undoes it. To find it, <b>swap x and y</b>, then solve for y.</p><div class=\"ex\"><div class=\"exh\">Worked example 2 · Find an inverse</div><div class=\"exl\">Find the inverse of y = 3x + 5.<br>Swap: x = 3y + 5. Subtract 5: x − 5 = 3y.<br>Divide by 3: <b>y = <span class=\"fq\"><span>x − 5</span><span>3</span></span></b>. Check: 4 → 17 → (17 − 5) ÷ 3 = 4 ✓</div></div><h4>Codes and ciphers</h4><p>Number the letters A = 1, B = 2, …, Z = 26. An <b>encryption function</b> changes each letter number x to a code number y; the inverse function decodes it. If y is bigger than 26, subtract 26 (as many times as needed) to get back into 1–26. This is called working <b>mod 26</b>: 31 (mod 26) = 5, which is E.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Letter</th><th>A</th><th>E</th><th>H</th><th>K</th><th>O</th><th>S</th><th>T</th><th>W</th><th>Z</th></tr><tr><td>Number</td><td>1</td><td>5</td><td>8</td><td>11</td><td>15</td><td>19</td><td>20</td><td>23</td><td>26</td></tr></table></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Encode and decode</div><div class=\"exl\">Code y = 3x + 2. Encode H: x = 8, y = 3 × 8 + 2 = 26, which is Z.<br>Decode with the inverse y = <span class=\"fq\"><span>x − 2</span><span>3</span></span>: Z = 26 gives (26 − 2) ÷ 3 = 8 = H ✓</div></div><div class=\"keybox\"><b>The multiplier must share no factor with 26.</b> With y = 2x + 3, A → 5 = E and N → 31 − 26 = 5 = E as well, so E cannot be decoded. Use multipliers such as 1, 3, 5, 7, 9, 11, … (odd, and not 13).</div><div class=\"ex\"><div class=\"exh\">Worked example 4 · When mod 26 is needed</div><div class=\"exl\">Code y = 3x + 1. Encode T: 3 × 20 + 1 = 61; 61 − 52 = 9, which is I.<br>Decode I = 9: (9 − 1) ÷ 3 is not a whole number, so add 26 and try again: (35 − 1) ÷ 3 is still not whole; add 26 once more: (61 − 1) ÷ 3 = <b>20 = T</b> ✓</div></div><div class=\"keybox\"><b>Undo in reverse order.</b> The code “multiply by 3, then add 1” is undone by “subtract 1, then divide by 3”.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s5\">Practise 4.5 →</button></div></section><section class=\"note\" id=\"n46\"><h2>4.6 Inequalities</h2><p class=\"lt\"><b>Objective:</b> Represent inequalities on a number line and solve inequalities.</p><h4>Symbols and number lines</h4><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Symbol</th><th>Meaning</th><th>Circle on the number line</th></tr><tr><td class=\"mono\">x &gt; 2</td><td>greater than 2</td><td>open (2 is not included)</td></tr><tr><td class=\"mono\">x ≥ 2</td><td>greater than or equal to 2 (at least 2)</td><td>closed / filled</td></tr><tr><td class=\"mono\">x &lt; 2</td><td>less than 2</td><td>open</td></tr><tr><td class=\"mono\">x ≤ 2</td><td>less than or equal to 2 (at most 2)</td><td>closed / filled</td></tr></table></div><svg class=\"figsvg\" viewBox=\"0 0 320 76\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">x > 2 : open circle, arrow right</text><line class=\"ln\" x1=\"8.0\" y1=\"42.0\" x2=\"312.0\" y2=\"42.0\"/><line x1=\"22.0\" y1=\"37\" x2=\"22.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"22.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><line x1=\"49.6\" y1=\"37\" x2=\"49.6\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"49.6\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−3</text><line x1=\"77.2\" y1=\"37\" x2=\"77.2\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"77.2\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><line x1=\"104.8\" y1=\"37\" x2=\"104.8\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"104.8\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><line x1=\"132.4\" y1=\"37\" x2=\"132.4\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"132.4\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"160.0\" y1=\"37\" x2=\"160.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"160.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"187.6\" y1=\"37\" x2=\"187.6\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"187.6\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"215.2\" y1=\"37\" x2=\"215.2\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"215.2\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"242.8\" y1=\"37\" x2=\"242.8\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"242.8\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"270.4\" y1=\"37\" x2=\"270.4\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"270.4\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"298.0\" y1=\"37\" x2=\"298.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"298.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"187.6\" y1=\"42\" x2=\"304.0\" y2=\"42\" style=\"stroke:var(--accent-text);stroke-width:4;stroke-linecap:round\"/><path d=\"M312.0,42 L302.0,36 L302.0,48 Z\" style=\"fill:var(--accent-text)\"/><circle cx=\"187.6\" cy=\"42\" r=\"5.5\" style=\"fill:var(--card);stroke:var(--accent-text);stroke-width:2.2\"/></svg><svg class=\"figsvg\" viewBox=\"0 0 320 76\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">x ≤ 2 : closed circle, arrow left</text><line class=\"ln\" x1=\"8.0\" y1=\"42.0\" x2=\"312.0\" y2=\"42.0\"/><line x1=\"22.0\" y1=\"37\" x2=\"22.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"22.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><line x1=\"49.6\" y1=\"37\" x2=\"49.6\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"49.6\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−3</text><line x1=\"77.2\" y1=\"37\" x2=\"77.2\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"77.2\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><line x1=\"104.8\" y1=\"37\" x2=\"104.8\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"104.8\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><line x1=\"132.4\" y1=\"37\" x2=\"132.4\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"132.4\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"160.0\" y1=\"37\" x2=\"160.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"160.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"187.6\" y1=\"37\" x2=\"187.6\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"187.6\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"215.2\" y1=\"37\" x2=\"215.2\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"215.2\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"242.8\" y1=\"37\" x2=\"242.8\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"242.8\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"270.4\" y1=\"37\" x2=\"270.4\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"270.4\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"298.0\" y1=\"37\" x2=\"298.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"298.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"16.0\" y1=\"42\" x2=\"187.6\" y2=\"42\" style=\"stroke:var(--accent-text);stroke-width:4;stroke-linecap:round\"/><path d=\"M8.0,42 L18.0,36 L18.0,48 Z\" style=\"fill:var(--accent-text)\"/><circle cx=\"187.6\" cy=\"42\" r=\"5.5\" style=\"fill:var(--accent-text);stroke:var(--accent-text);stroke-width:2.2\"/></svg><p>A <b>double inequality</b> such as −1 &lt; x ≤ 3 shows all numbers between two values:</p><svg class=\"figsvg\" viewBox=\"0 0 320 76\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1 < x ≤ 3</text><line class=\"ln\" x1=\"8.0\" y1=\"42.0\" x2=\"312.0\" y2=\"42.0\"/><line x1=\"22.0\" y1=\"37\" x2=\"22.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"22.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><line x1=\"49.6\" y1=\"37\" x2=\"49.6\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"49.6\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−3</text><line x1=\"77.2\" y1=\"37\" x2=\"77.2\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"77.2\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><line x1=\"104.8\" y1=\"37\" x2=\"104.8\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"104.8\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><line x1=\"132.4\" y1=\"37\" x2=\"132.4\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"132.4\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"160.0\" y1=\"37\" x2=\"160.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"160.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"187.6\" y1=\"37\" x2=\"187.6\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"187.6\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"215.2\" y1=\"37\" x2=\"215.2\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"215.2\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"242.8\" y1=\"37\" x2=\"242.8\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"242.8\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"270.4\" y1=\"37\" x2=\"270.4\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"270.4\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"298.0\" y1=\"37\" x2=\"298.0\" y2=\"47\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"298.0\" y=\"59.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"104.8\" y1=\"42\" x2=\"215.2\" y2=\"42\" style=\"stroke:var(--accent-text);stroke-width:4;stroke-linecap:round\"/><circle cx=\"104.8\" cy=\"42\" r=\"5.5\" style=\"fill:var(--card);stroke:var(--accent-text);stroke-width:2.2\"/><circle cx=\"215.2\" cy=\"42\" r=\"5.5\" style=\"fill:var(--accent-text);stroke:var(--accent-text);stroke-width:2.2\"/></svg><div class=\"keybox\"><b>Read from the variable.</b> 5 &gt; x means the same as x &lt; 5. Rewrite with the variable on the left before you draw it.</div><h4>Solving inequalities</h4><p>Solve an inequality exactly like an equation, with one extra rule: when you <b>multiply or divide both sides by a negative number, reverse the inequality sign</b>. (For example, 3 &gt; 1 but −3 &lt; −1.)</p><div class=\"ex\"><div class=\"exh\">Worked example 1</div><div class=\"exl\">Solve 2x − 3 &gt; 7.<br>Add 3: 2x &gt; 10. Divide by 2: <b>x &gt; 5</b> (open circle at 5, arrow right).</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Dividing by a negative</div><div class=\"exl\">Solve −4x ≤ 8.<br>Divide by −4 and reverse the sign: <b>x ≥ −2</b>.<br>Check a value: x = 0 gives 0 ≤ 8 ✓; x = −3 gives 12 ≤ 8 ✗.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Both sides</div><div class=\"exl\">Solve 3(x − 1) &lt; 5x + 7.<br>Expand: 3x − 3 &lt; 5x + 7. Subtract 3x: −3 &lt; 2x + 7.<br>Subtract 7: −10 &lt; 2x, so −5 &lt; x, i.e. <b>x &gt; −5</b>.</div></div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s6\">Practise 4.6 →</button></div></section><section class=\"note\" id=\"nsum\"><h2>Unit checklist</h2><ul><li>I can name the terms, coefficients and constant of an expression.</li><li>I can classify a polynomial by its number of terms and its degree, and write it in standard form.</li><li>I can collect like terms and expand brackets, including negative multipliers.</li><li>I can write expressions from words and use algebra to explain number tricks.</li><li>I can solve equations with brackets, fractions and the variable on both sides, and check my answer.</li><li>I can write an equation for a problem, and find an inverse function to decode a message.</li><li>I can draw and solve inequalities, reversing the sign when I multiply or divide by a negative.</li></ul><div class=\"hub-btns\" style=\"margin-top:10px\"><button class=\"hub-btn\" data-go=\"s7\">Test A</button><button class=\"hub-btn\" data-go=\"s8\">Test B</button><button class=\"hub-btn\" data-go=\"s9\">Test C</button><button class=\"hub-btn\" data-go=\"s10\">Test D</button><button class=\"hub-btn primary\" data-go=\"report\">📊 Report</button></div></section>";
var REPORT = [["s7", "A", "Knowing and understanding"], ["s8", "B", "Investigating patterns"], ["s9", "C", "Communicating"], ["s10", "D", "Applying mathematics in real-life contexts"]];
var SECTIONS = [{"id": "s1", "label": "4.1 Polynomials", "sub": "Classifying polynomials — number of terms, degree and standard form", "slides": [{"kind": "mcq", "text": "How is 7m² − 4m + 9 classified by its number of terms?", "opts": ["trinomial", "quadratic binomial", "monomial", "binomial"], "correct": 0, "tag": "", "sol": "It has three terms (7m², −4m and 9), so it is a trinomial."}, {"kind": "mcq", "text": "What is the degree of the term 5x³y²?", "opts": ["6", "2", "3", "5"], "correct": 3, "tag": "", "sol": "Add the exponents of the variables: 3 + 2 = 5."}, {"kind": "mcq", "text": "What is the degree of 4a²b − 9ab³ + 2?", "opts": ["7", "6", "3", "4"], "correct": 3, "tag": "", "sol": "Term degrees: 2 + 1 = 3, 1 + 3 = 4 and 0. The highest is 4."}, {"kind": "mcq", "text": "Which expression is a binomial?", "opts": ["12", "p² + p + 1", "3p − 8q", "−11pqr"], "correct": 2, "tag": "", "sol": "3p − 8q has two terms. −11pqr and 12 are monomials; p² + p + 1 is a trinomial."}, {"kind": "mcq", "text": "Which is 6 − 2k + 5k³ − k² written in standard form?", "opts": ["−k² + 5k³ − 2k + 6", "5k³ − 2k − k² + 6", "6 − 2k − k² + 5k³", "5k³ − k² − 2k + 6"], "correct": 3, "tag": "", "sol": "Standard form lists terms from the highest degree down: k³, k², k, constant."}, {"kind": "mcq", "text": "How is 9 − 4x² + x best described?", "opts": ["a quadratic binomial", "a quadratic trinomial", "a linear trinomial", "a cubic trinomial"], "correct": 1, "tag": "", "sol": "Three terms, highest degree 2: a quadratic trinomial."}, {"kind": "mcq", "text": "Which expression is NOT a polynomial?", "opts": ["x³ − x", "4/x + 3", "0.5x² − 1", "−7"], "correct": 1, "tag": "", "sol": "4/x has the variable in the denominator (x⁻¹), so it is not a polynomial. A constant such as −7 is a polynomial of degree 0."}, {"kind": "mcq", "text": "In −3n⁴ + 8n² − n + 10, what are the coefficient of n² and the constant term?", "opts": ["8 and −1", "8 and 10", "2 and 10", "−3 and 10"], "correct": 1, "tag": "", "sol": "The n² term is 8n², so its coefficient is 8. The term with no variable is 10."}, {"kind": "blank", "p": "Look at the polynomial 3x² − 7x + 2x⁴ − 1.", "tag": "", "marks": "", "flat": [{"t": "Number of terms = __B1__", "a": {"B1": "4"}}, {"t": "Degree = __B1__", "a": {"B1": "4"}}, {"t": "In standard form: __B1__", "a": {"B1": "2x^4+3x^2-7x-1"}, "expr": true}, {"t": "Leading coefficient = __B1__", "a": {"B1": "2"}}], "sol": "3x², −7x, 2x⁴ and −1: four terms.\nThe highest exponent is 4 (in 2x⁴).\nDescending powers: 2x⁴ + 3x² − 7x − 1.\nThe coefficient of the first term in standard form is 2."}, {"kind": "blank", "p": "For each term, give the coefficient and the degree.", "tag": "", "marks": "", "flat": [{"t": "−6a²b³c: coefficient __B1__, degree __B2__", "a": {"B1": "-6", "B2": "6"}}, {"t": "m: coefficient __B1__, degree __B2__", "a": {"B1": "1", "B2": "1"}}, {"t": "11: degree __B1__", "a": {"B1": "0"}}], "sol": "Coefficient −6; degree 2 + 3 + 1 = 6.\nm = 1m¹: coefficient 1, degree 1.\nA constant has no variable, so its degree is 0."}, {"kind": "blank", "p": "Classify 4y − 9.", "tag": "", "marks": "", "flat": [{"t": "Number of terms = __B1__", "a": {"B1": "2"}}, {"t": "By number of terms it is a __B1__.", "a": {"B1": "binomial"}, "expr": "words"}, {"t": "By degree it is __B1__.", "a": {"B1": "linear"}, "expr": "words"}], "sol": "4y and −9.\nTwo terms: binomial.\nDegree 1: linear."}, {"kind": "blank", "p": "Look at p⁵ − 3p²q² + 12.", "tag": "", "marks": "", "flat": [{"t": "Degrees of the three terms: __B1__, __B2__ and __B3__", "a": {"B1": "5", "B2": "4", "B3": "0"}}, {"t": "Degree of the polynomial = __B1__", "a": {"B1": "5"}}, {"t": "By degree it is __B1__.", "a": {"B1": "quintic"}, "expr": "words"}], "sol": "p⁵ has degree 5; p²q² has 2 + 2 = 4; 12 has 0.\nThe highest is 5.\nDegree 5 is called quintic."}, {"kind": "blank", "p": "Write 5 + x³ − 2x in standard form and name it.", "tag": "", "marks": "", "flat": [{"t": "Standard form: __B1__", "a": {"B1": "x^3-2x+5"}, "expr": true}, {"t": "It is a cubic __B1__.", "a": {"B1": "trinomial"}, "expr": "words"}], "sol": "Descending powers: x³ − 2x + 5.\nThree terms with degree 3: a cubic trinomial."}]}, {"id": "s2", "label": "4.2 Simplifying", "sub": "Simplifying and expanding — like terms and the distributive property", "slides": [{"kind": "mcq", "text": "Which pair are like terms?", "opts": ["3a²b and 3ab²", "4m and 4m²", "5ab² and −2ab²", "7x and 7y"], "correct": 2, "tag": "", "sol": "5ab² and −2ab² have the same letters with the same exponents. The others differ in variables or exponents."}, {"kind": "mcq", "text": "Simplify 6k + 2 − 4k + 9.", "opts": ["2k + 11", "13k", "10k + 11", "2k + 7"], "correct": 0, "tag": "", "sol": "6k − 4k = 2k and 2 + 9 = 11."}, {"kind": "mcq", "text": "Simplify 3x² + 4x − x² − 7x.", "opts": ["2x² + 11x", "−x", "4x² − 3x", "2x² − 3x"], "correct": 3, "tag": "", "sol": "3x² − x² = 2x² and 4x − 7x = −3x. x² terms and x terms are not like terms."}, {"kind": "mcq", "text": "Expand 4(3m − 5).", "opts": ["7m − 9", "12m + 20", "12m − 5", "12m − 20"], "correct": 3, "tag": "", "sol": "4 × 3m = 12m and 4 × (−5) = −20."}, {"kind": "mcq", "text": "Expand −2(a − 6).", "opts": ["−2a − 12", "−2a + 12", "−2a − 6", "2a − 12"], "correct": 1, "tag": "", "sol": "−2 × a = −2a and −2 × (−6) = +12."}, {"kind": "mcq", "text": "Expand and simplify 3(n + 4) + 2(n − 1).", "opts": ["5n + 10", "5n + 14", "5n + 11", "6n + 10"], "correct": 0, "tag": "", "sol": "3n + 12 + 2n − 2 = 5n + 10."}, {"kind": "mcq", "text": "Simplify 5xy − 3yx + 2x.", "opts": ["2xy + 2x", "4xy", "8xy + 2x", "2xy + 2"], "correct": 0, "tag": "", "sol": "yx is the same as xy, so 5xy − 3xy = 2xy. 2x is not a like term."}, {"kind": "mcq", "text": "Which expression is equivalent to 7 − 2(t − 3)?", "opts": ["13 + 2t", "13 − 2t", "5t − 15", "1 − 2t"], "correct": 1, "tag": "", "sol": "−2(t − 3) = −2t + 6, so 7 − 2t + 6 = 13 − 2t. (5t − 15 wrongly does 7 − 2 first.)"}, {"kind": "blank", "p": "Simplify 8a + 3b − 5a + b − 6.", "tag": "", "marks": "", "flat": [{"t": "The a terms give __B1__", "a": {"B1": "3a"}, "expr": true}, {"t": "The b terms give __B1__", "a": {"B1": "4b"}, "expr": true}, {"t": "Simplified: __B1__", "a": {"B1": "3a+4b-6"}, "expr": true}], "sol": "8a − 5a = 3a.\n3b + b = 4b.\n3a + 4b − 6."}, {"kind": "blank", "p": "Simplify 4g² − 2g + 7 − g² + 5g − 10.", "tag": "", "marks": "", "flat": [{"t": "Simplified: __B1__", "a": {"B1": "3g^2+3g-3"}, "expr": true}, {"t": "The coefficient of g² is __B1__.", "a": {"B1": "3"}}], "sol": "4g² − g² = 3g², −2g + 5g = 3g, 7 − 10 = −3: 3g² + 3g − 3.\n3."}, {"kind": "blank", "p": "Expand and simplify 6(2w + 1) − 4(w − 3).", "tag": "", "marks": "", "flat": [{"t": "6(2w + 1) = __B1__", "a": {"B1": "12w+6"}, "expr": true}, {"t": "−4(w − 3) = __B1__", "a": {"B1": "-4w+12"}, "expr": true}, {"t": "Simplified: __B1__", "a": {"B1": "8w+18"}, "expr": true}], "sol": "6 × 2w = 12w and 6 × 1 = 6.\n−4 × w = −4w and −4 × (−3) = +12.\n12w − 4w = 8w and 6 + 12 = 18."}, {"kind": "blank", "p": "The rectangle has width 5 and length 2x + 9. Use the area model.", "tag": "", "marks": "", "flat": [{"t": "Area of the left part = __B1__", "a": {"B1": "10x"}, "expr": true}, {"t": "Area of the right part = __B1__", "a": {"B1": "45"}}, {"t": "So 5(2x + 9) = __B1__", "a": {"B1": "10x+45"}, "expr": true}], "sol": "5 × 2x = 10x.\n5 × 9 = 45.\n10x + 45.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 120\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"al\" x=\"30.0\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><rect x=\"44.0\" y=\"26\" width=\"146.4\" height=\"70\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.4\"/><text class=\"al\" x=\"117.2\" y=\"16.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2x</text><text class=\"lb\" x=\"117.2\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">?</text><rect x=\"190.4\" y=\"26\" width=\"97.6\" height=\"70\" style=\"fill:var(--gold-soft);stroke:var(--ink);stroke-width:1.4\"/><text class=\"al\" x=\"239.2\" y=\"16.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><text class=\"lb\" x=\"239.2\" y=\"61.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">?</text></svg>"}, {"kind": "blank", "p": "Expand and simplify x(x + 5) − 2x.", "tag": "", "marks": "", "flat": [{"t": "x(x + 5) = __B1__", "a": {"B1": "x^2+5x"}, "expr": true}, {"t": "Simplified: __B1__", "a": {"B1": "x^2+3x"}, "expr": true}], "sol": "x × x = x² and x × 5 = 5x.\n5x − 2x = 3x, so x² + 3x."}]}, {"id": "s3", "label": "4.3 Expressions", "sub": "Writing expressions and number tricks — words to algebra, and justifying tricks", "slides": [{"kind": "mcq", "text": "Write “7 less than twice a number n” as an expression.", "opts": ["7 − 2n", "2n + 7", "2n − 7", "2(n − 7)"], "correct": 2, "tag": "", "sol": "Twice n is 2n; 7 less than that is 2n − 7."}, {"kind": "mcq", "text": "Three consecutive integers start at n. What is their sum?", "opts": ["3n + 2", "3n", "3n + 3", "n + 3"], "correct": 2, "tag": "", "sol": "n + (n + 1) + (n + 2) = 3n + 3."}, {"kind": "mcq", "text": "A cinema ticket costs ₹t and a tub of popcorn costs ₹p. What do 4 tickets and 2 tubs cost?", "opts": ["₹(4t + 2p)", "₹8tp", "₹(4 + t)(2 + p)", "₹6tp"], "correct": 0, "tag": "", "sol": "4 tickets cost 4t and 2 tubs cost 2p; add them."}, {"kind": "mcq", "text": "Which instructions match the expression 3(x + 5)?", "opts": ["Add 5 to a number, then multiply by 3", "Multiply a number by 3, then add 5", "Multiply a number by 5, then add 3", "Add 3 to a number, then multiply by 5"], "correct": 0, "tag": "", "sol": "The bracket is done first: x + 5, then the whole thing is multiplied by 3."}, {"kind": "mcq", "text": "A two-digit number has tens digit a and units digit b. What is its value?", "opts": ["ab", "10b + a", "10a + b", "a + b"], "correct": 2, "tag": "", "sol": "a tens and b units: 10a + b. (For example, 47 = 10 × 4 + 7.)"}, {"kind": "mcq", "text": "Think of a number n, double it, add 10, halve the result, then subtract n. What is the answer?", "opts": ["10", "2n", "5", "n"], "correct": 2, "tag": "", "sol": "(2n + 10) ÷ 2 = n + 5, and n + 5 − n = 5 for every n."}, {"kind": "mcq", "text": "On a calendar, a date is n. What is the date directly below it?", "opts": ["7n", "n + 7", "n − 7", "n + 1"], "correct": 1, "tag": "", "sol": "The next row is one week later: n + 7."}, {"kind": "mcq", "text": "For any integer n, which expression is always odd?", "opts": ["2n + 1", "n + 1", "2n", "3n"], "correct": 0, "tag": "", "sol": "2n is always even, so 2n + 1 is always one more than an even number."}, {"kind": "blank", "p": "Justify this trick: think of a number n, multiply by 4, add 12, divide by 4, then subtract the number you first thought of.", "tag": "", "marks": "", "flat": [{"t": "After “multiply by 4, add 12”: __B1__", "a": {"B1": "4n+12"}, "expr": true}, {"t": "After dividing by 4: __B1__", "a": {"B1": "n+3"}, "expr": true}, {"t": "After subtracting n, the answer is always __B1__.", "a": {"B1": "3"}}], "sol": "4n + 12.\n(4n + 12) ÷ 4 = n + 3.\nn + 3 − n = 3, whatever n is."}, {"kind": "blank", "p": "On a calendar, three dates in a column are n, n + 7 and n + 14.", "tag": "", "marks": "", "flat": [{"t": "Their sum is __B1__", "a": {"B1": "3n+21"}, "expr": true}, {"t": "This equals 3 × (__B1__), three times the middle date.", "a": {"B1": "n+7"}, "expr": true}, {"t": "If the sum is 57, the top date is __B1__.", "a": {"B1": "12"}}], "sol": "n + n + 7 + n + 14 = 3n + 21.\n3n + 21 = 3(n + 7), and n + 7 is the middle date.\n3n + 21 = 57, so 3n = 36 and n = 12 (dates 12, 19, 26)."}, {"kind": "blank", "p": "Write each phrase as an expression.", "tag": "", "marks": "", "flat": [{"t": "5 more than a third of x: __B1__", "a": {"B1": "x/3+5"}, "expr": true}, {"t": "the product of p and q, halved: __B1__", "a": {"B1": "pq/2"}, "expr": true}, {"t": "₹500 shared equally among k friends: ₹__B1__", "a": {"B1": "500/k"}, "expr": true}], "sol": "A third of x is x/3; add 5.\npq ÷ 2.\n500 ÷ k."}, {"kind": "blank", "p": "A two-digit number has tens digit a and units digit b. Reverse the digits and subtract.", "tag": "", "marks": "", "flat": [{"t": "The reversed number is __B1__", "a": {"B1": "10b+a"}, "expr": true}, {"t": "(10a + b) − (10b + a) = __B1__", "a": {"B1": "9a-9b"}, "expr": true}, {"t": "So 73 − 37 = __B1__, which is 9 × 4.", "a": {"B1": "36"}}], "sol": "b tens and a units: 10b + a.\n10a − a = 9a and b − 10b = −9b.\n73 − 37 = 36 = 9 × (7 − 3)."}, {"kind": "blank", "p": "Four consecutive integers start at n.", "tag": "", "marks": "", "flat": [{"t": "Their sum is __B1__", "a": {"B1": "4n+6"}, "expr": true}, {"t": "Is the sum always even? __B1__", "a": {"B1": "yes"}, "expr": "words", "accept": ["y"]}], "sol": "n + (n + 1) + (n + 2) + (n + 3) = 4n + 6.\n4n + 6 = 2(2n + 3), which is 2 × a whole number, so yes."}]}, {"id": "s4", "label": "4.4 Equations", "sub": "Solving equations — brackets, fractions and variables on both sides", "slides": [{"kind": "mcq", "text": "Solve x + 13 = 4.", "opts": ["x = 17", "x = −9", "x = 9", "x = −17"], "correct": 1, "tag": "", "sol": "Subtract 13 from both sides: x = 4 − 13 = −9."}, {"kind": "mcq", "text": "Solve 6p = −42.", "opts": ["p = −36", "p = −7", "p = −252", "p = 7"], "correct": 1, "tag": "", "sol": "Divide both sides by 6: −42 ÷ 6 = −7."}, {"kind": "mcq", "text": "Solve 3m − 7 = 20.", "opts": ["m = {13/3}", "m = 9", "m = 27", "m = 81"], "correct": 1, "tag": "", "sol": "Add 7: 3m = 27. Divide by 3: m = 9."}, {"kind": "mcq", "text": "Solve k/4 − 2 = 5.", "opts": ["k = 20", "k = 12", "k = 28", "k = 1.75"], "correct": 2, "tag": "", "sol": "Add 2: k/4 = 7. Multiply by 4: k = 28."}, {"kind": "mcq", "text": "Solve 8w + 5 = 3w + 30.", "opts": ["w = 3.18", "w = 25", "w = 7", "w = 5"], "correct": 3, "tag": "", "sol": "Subtract 3w: 5w + 5 = 30. Subtract 5: 5w = 25, so w = 5."}, {"kind": "mcq", "text": "Solve 2(3y − 1) = 22.", "opts": ["y = 3.5", "y = 4", "y = {23/6}", "y = 12"], "correct": 1, "tag": "", "sol": "Expand: 6y − 2 = 22, so 6y = 24 and y = 4."}, {"kind": "mcq", "text": "What is the best first step to solve 5x + 4 = 2x − 11?", "opts": ["Add 5x to both sides", "Subtract 2x from both sides", "Subtract 11 from both sides", "Divide both sides by 4"], "correct": 1, "tag": "", "sol": "Removing the smaller x term (2x) leaves 3x + 4 = −11, with x on one side only."}, {"kind": "mcq", "text": "Which value is a solution of 4(t + 3) = 7t?", "opts": ["t = −4", "t = 12", "t = 3", "t = 4"], "correct": 3, "tag": "", "sol": "Check t = 4: 4 × 7 = 28 and 7 × 4 = 28 ✓. (4t + 12 = 7t gives 3t = 12, t = 4.)"}, {"kind": "blank", "p": "Solve 4g − 9 = 2g + 7.", "tag": "", "marks": "", "flat": [{"t": "Subtract 2g from both sides: __B1__g − 9 = 7", "a": {"B1": "2"}}, {"t": "Add 9 to both sides: 2g = __B1__", "a": {"B1": "16"}}, {"t": "g = __B1__", "a": {"B1": "8"}}], "sol": "4g − 2g = 2g.\n7 + 9 = 16.\n16 ÷ 2 = 8. Check: 23 = 23 ✓", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 132\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><path d=\"M150.0,54 L132.0,118 L168.0,118 Z\" style=\"fill:var(--paper-2);stroke:var(--ink);stroke-width:1.4\"/><line x1=\"30.0\" y1=\"54\" x2=\"270.0\" y2=\"54\" style=\"stroke:var(--ink);stroke-width:3;stroke-linecap:round\"/><line x1=\"60.0\" y1=\"54\" x2=\"60.0\" y2=\"46\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"10.0\" y=\"14\" width=\"100\" height=\"32\" rx=\"6\" style=\"fill:var(--gold-soft);stroke:var(--gold);stroke-width:1.4\"/><text class=\"lb\" x=\"60.0\" y=\"30.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4g − 9</text><line x1=\"240.0\" y1=\"54\" x2=\"240.0\" y2=\"46\" style=\"stroke:var(--ink);stroke-width:1.4\"/><rect x=\"190.0\" y=\"14\" width=\"100\" height=\"32\" rx=\"6\" style=\"fill:var(--gold-soft);stroke:var(--gold);stroke-width:1.4\"/><text class=\"lb\" x=\"240.0\" y=\"30.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2g + 7</text></svg>"}, {"kind": "blank", "p": "Solve 3(c + 5) = 5(c − 1).", "tag": "", "marks": "", "flat": [{"t": "Expand: 3c + 15 = __B1__", "a": {"B1": "5c-5"}, "expr": true}, {"t": "Subtract 3c and add 5: 20 = __B1__c", "a": {"B1": "2"}}, {"t": "c = __B1__", "a": {"B1": "10"}}], "sol": "5 × c − 5 × 1 = 5c − 5.\n15 + 5 = 20 and 5c − 3c = 2c.\nc = 10. Check: 3 × 15 = 45 and 5 × 9 = 45 ✓"}, {"kind": "blank", "p": "Solve 2d/5 + 3 = 11.", "tag": "", "marks": "", "flat": [{"t": "Subtract 3: 2d/5 = __B1__", "a": {"B1": "8"}}, {"t": "Multiply by 5: 2d = __B1__", "a": {"B1": "40"}}, {"t": "d = __B1__", "a": {"B1": "20"}}], "sol": "11 − 3 = 8.\n8 × 5 = 40.\n40 ÷ 2 = 20."}, {"kind": "blank", "p": "Solve 7 − 3r = 19.", "tag": "", "marks": "", "flat": [{"t": "Subtract 7: −3r = __B1__", "a": {"B1": "12"}}, {"t": "r = __B1__", "a": {"B1": "-4"}}], "sol": "19 − 7 = 12.\n12 ÷ (−3) = −4. Check: 7 − 3(−4) = 7 + 12 = 19 ✓"}, {"kind": "blank", "p": "Solve (x − 4)/3 = x − 10.", "tag": "", "marks": "", "flat": [{"t": "Multiply both sides by 3: x − 4 = __B1__", "a": {"B1": "3x-30"}, "expr": true}, {"t": "Subtract x and add 30: __B1__ = 2x", "a": {"B1": "26"}}, {"t": "x = __B1__", "a": {"B1": "13"}}], "sol": "3(x − 10) = 3x − 30.\n−4 + 30 = 26 and 3x − x = 2x.\nx = 13. Check: (13 − 4) ÷ 3 = 3 and 13 − 10 = 3 ✓"}]}, {"id": "s5", "label": "4.5 Writing equations", "sub": "Writing equations and inverse functions — problems, codes and ciphers", "slides": [{"kind": "mcq", "text": "Three consecutive integers add up to 84. Which equation fits, if the smallest is n?", "opts": ["3n = 84", "n + 3 = 84", "3n + 6 = 84", "3n + 3 = 84"], "correct": 3, "tag": "", "sol": "n + (n + 1) + (n + 2) = 3n + 3."}, {"kind": "mcq", "text": "Three consecutive integers add up to 84. What is the smallest?", "opts": ["28", "26", "27", "81"], "correct": 2, "tag": "", "sol": "3n + 3 = 84, so 3n = 81 and n = 27 (27 + 28 + 29 = 84)."}, {"kind": "mcq", "text": "I think of a number, multiply it by 5 and subtract 7. The result is 38. What was my number?", "opts": ["7", "6.2", "45", "9"], "correct": 3, "tag": "", "sol": "5n − 7 = 38, so 5n = 45 and n = 9."}, {"kind": "mcq", "text": "What is the inverse of y = x + 9?", "opts": ["y = 9 − x", "y = 9x", "y = x − 9", "y = x/9"], "correct": 2, "tag": "", "sol": "Swap: x = y + 9, so y = x − 9."}, {"kind": "mcq", "text": "What is the inverse of y = 4x − 3?", "opts": ["y = x/4 + 3", "y = (x + 3)/4", "y = (x − 3)/4", "y = 4x + 3"], "correct": 1, "tag": "", "sol": "Swap: x = 4y − 3. Add 3: x + 3 = 4y. Divide by 4: y = (x + 3)/4."}, {"kind": "mcq", "text": "What is 57 (mod 26)?", "opts": ["7, the letter G", "31, the letter E", "5, the letter E", "2, the letter B"], "correct": 2, "tag": "", "sol": "57 − 26 − 26 = 5, and letter 5 is E."}, {"kind": "mcq", "text": "With the code y = x + 5 (A = 1, …, Z = 26, mod 26), what does W (23) become?", "opts": ["B", "R", "C", "A"], "correct": 0, "tag": "", "sol": "23 + 5 = 28; 28 − 26 = 2, which is B."}, {"kind": "mcq", "text": "Riya is 4 years older than twice her brother's age b. Riya is 20. Which equation gives b?", "opts": ["2b + 4 = 20", "b + 4 = 20", "2(b + 4) = 20", "4b + 2 = 20"], "correct": 0, "tag": "", "sol": "Twice b is 2b; 4 more is 2b + 4. (So b = 8.)"}, {"kind": "blank", "p": "Four consecutive integers add up to 106. Let the smallest be n.", "tag": "", "marks": "", "flat": [{"t": "Their sum is __B1__", "a": {"B1": "4n+6"}, "expr": true}, {"t": "4n + 6 = 106, so n = __B1__", "a": {"B1": "25"}}, {"t": "The largest integer is __B1__.", "a": {"B1": "28"}}], "sol": "n + (n + 1) + (n + 2) + (n + 3) = 4n + 6.\n4n = 100, n = 25.\n25, 26, 27, 28 (sum 106 ✓)."}, {"kind": "blank", "p": "A rectangle's length is 3 cm more than twice its width w. Its perimeter is 54 cm.", "tag": "", "marks": "", "flat": [{"t": "Length = __B1__", "a": {"B1": "2w+3"}, "expr": true}, {"t": "Perimeter = 2w + 2(2w + 3) = __B1__", "a": {"B1": "6w+6"}, "expr": true}, {"t": "w = __B1__ cm", "a": {"B1": "8"}}, {"t": "Length = __B1__ cm", "a": {"B1": "19"}}], "sol": "Twice w plus 3: 2w + 3.\n2w + 4w + 6 = 6w + 6.\n6w + 6 = 54, 6w = 48, w = 8.\n2 × 8 + 3 = 19. Check: 2 × 8 + 2 × 19 = 54 ✓"}, {"kind": "blank", "p": "Find the inverse of y = 5x + 2.", "tag": "", "marks": "", "flat": [{"t": "Swap x and y: x = __B1__", "a": {"B1": "5y+2"}, "expr": true}, {"t": "Inverse: y = __B1__", "a": {"B1": "(x-2)/5"}, "expr": true}, {"t": "Check: y = 5x + 2 sends 3 to 17, and the inverse sends 17 to __B1__.", "a": {"B1": "3"}}], "sol": "x = 5y + 2.\nx − 2 = 5y, so y = (x − 2)/5.\n(17 − 2) ÷ 5 = 3 ✓"}, {"kind": "blank", "p": "A code uses y = 3x + 2 with A = 1, …, Z = 26, working mod 26.", "tag": "", "marks": "", "flat": [{"t": "D (4) is encoded as __B1__", "a": {"B1": "N"}, "expr": "words"}, {"t": "Y (25) is encoded as __B1__", "a": {"B1": "Y"}, "expr": "words"}, {"t": "The code letter K (11) decodes to __B1__", "a": {"B1": "C"}, "expr": "words"}], "sol": "3 × 4 + 2 = 14 = N.\n3 × 25 + 2 = 77; 77 − 52 = 25 = Y (this letter is not changed!).\nInverse (x − 2)/3: (11 − 2) ÷ 3 = 3 = C."}, {"kind": "blank", "p": "Aman has ₹x. Bina has ₹150 more than Aman. Together they have ₹910.", "tag": "", "marks": "", "flat": [{"t": "Equation: __B1__ = 910", "a": {"B1": "2x+150"}, "expr": true}, {"t": "x = __B1__", "a": {"B1": "380"}}, {"t": "Bina has ₹__B1__.", "a": {"B1": "530"}}], "sol": "x + (x + 150) = 2x + 150.\n2x = 760, x = 380.\n380 + 150 = 530. Check: 380 + 530 = 910 ✓"}]}, {"id": "s6", "label": "4.6 Inequalities", "sub": "Inequalities — number lines and solving", "slides": [{"kind": "mcq", "text": "Which inequality does the number line show?", "opts": ["x < 3", "x ≤ 3", "x ≥ 3", "x > 3"], "correct": 3, "tag": "", "sol": "Open circle at 3 (3 not included) and the arrow points right (bigger numbers): x > 3.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 62\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line class=\"ln\" x1=\"8.0\" y1=\"28.0\" x2=\"312.0\" y2=\"28.0\"/><line x1=\"22.0\" y1=\"23\" x2=\"22.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"22.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><line x1=\"49.6\" y1=\"23\" x2=\"49.6\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"49.6\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−3</text><line x1=\"77.2\" y1=\"23\" x2=\"77.2\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"77.2\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><line x1=\"104.8\" y1=\"23\" x2=\"104.8\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"104.8\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><line x1=\"132.4\" y1=\"23\" x2=\"132.4\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"132.4\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"160.0\" y1=\"23\" x2=\"160.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"160.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"187.6\" y1=\"23\" x2=\"187.6\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"187.6\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"215.2\" y1=\"23\" x2=\"215.2\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"215.2\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"242.8\" y1=\"23\" x2=\"242.8\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"242.8\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"270.4\" y1=\"23\" x2=\"270.4\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"270.4\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"298.0\" y1=\"23\" x2=\"298.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"298.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"215.2\" y1=\"28\" x2=\"304.0\" y2=\"28\" style=\"stroke:var(--accent-text);stroke-width:4;stroke-linecap:round\"/><path d=\"M312.0,28 L302.0,22 L302.0,34 Z\" style=\"fill:var(--accent-text)\"/><circle cx=\"215.2\" cy=\"28\" r=\"5.5\" style=\"fill:var(--card);stroke:var(--accent-text);stroke-width:2.2\"/></svg>"}, {"kind": "mcq", "text": "Which inequality does the number line show?", "opts": ["x ≥ −2", "x > −2", "x < −2", "x ≤ −2"], "correct": 3, "tag": "", "sol": "Closed circle at −2 (included) and the arrow points left: x ≤ −2.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 62\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line class=\"ln\" x1=\"8.0\" y1=\"28.0\" x2=\"312.0\" y2=\"28.0\"/><line x1=\"22.0\" y1=\"23\" x2=\"22.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"22.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><line x1=\"49.6\" y1=\"23\" x2=\"49.6\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"49.6\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−5</text><line x1=\"77.2\" y1=\"23\" x2=\"77.2\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"77.2\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><line x1=\"104.8\" y1=\"23\" x2=\"104.8\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"104.8\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−3</text><line x1=\"132.4\" y1=\"23\" x2=\"132.4\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"132.4\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><line x1=\"160.0\" y1=\"23\" x2=\"160.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"160.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><line x1=\"187.6\" y1=\"23\" x2=\"187.6\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"187.6\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"215.2\" y1=\"23\" x2=\"215.2\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"215.2\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"242.8\" y1=\"23\" x2=\"242.8\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"242.8\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"270.4\" y1=\"23\" x2=\"270.4\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"270.4\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"298.0\" y1=\"23\" x2=\"298.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"298.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"16.0\" y1=\"28\" x2=\"132.4\" y2=\"28\" style=\"stroke:var(--accent-text);stroke-width:4;stroke-linecap:round\"/><path d=\"M8.0,28 L18.0,22 L18.0,34 Z\" style=\"fill:var(--accent-text)\"/><circle cx=\"132.4\" cy=\"28\" r=\"5.5\" style=\"fill:var(--accent-text);stroke:var(--accent-text);stroke-width:2.2\"/></svg>"}, {"kind": "mcq", "text": "How is x ≥ −1 shown on a number line?", "opts": ["Open circle at −1, arrow to the left", "Closed circle at −1, arrow to the left", "Open circle at −1, arrow to the right", "Closed circle at −1, arrow to the right"], "correct": 3, "tag": "", "sol": "≥ includes −1, so the circle is closed; “greater” means the arrow points right."}, {"kind": "mcq", "text": "Solve 2x + 5 < 17.", "opts": ["x < 6", "x > 6", "x < 8", "x < 11"], "correct": 0, "tag": "", "sol": "Subtract 5: 2x < 12. Divide by 2 (positive, so no change): x < 6."}, {"kind": "mcq", "text": "Solve −3y ≥ 12.", "opts": ["y ≥ −4", "y ≤ −4", "y ≥ 4", "y ≤ 4"], "correct": 1, "tag": "", "sol": "Divide by −3 and reverse the sign: y ≤ −4."}, {"kind": "mcq", "text": "Solve 5 − 2k > 11.", "opts": ["k < −3", "k > 3", "k < 3", "k > −3"], "correct": 0, "tag": "", "sol": "Subtract 5: −2k > 6. Divide by −2 and reverse: k < −3."}, {"kind": "mcq", "text": "Which value is NOT a solution of 4n − 1 ≤ 11?", "opts": ["−2", "3", "0", "3.5"], "correct": 3, "tag": "", "sol": "4n ≤ 12, so n ≤ 3. 3.5 is greater than 3."}, {"kind": "mcq", "text": "How many integers satisfy −2 < x ≤ 4?", "opts": ["6", "7", "8", "5"], "correct": 0, "tag": "", "sol": "−1, 0, 1, 2, 3, 4: six integers (−2 is not included, 4 is)."}, {"kind": "blank", "p": "Solve 3x − 4 ≥ 11.", "tag": "", "marks": "", "flat": [{"t": "Add 4: 3x ≥ __B1__", "a": {"B1": "15"}}, {"t": "x ≥ __B1__", "a": {"B1": "5"}}, {"t": "On a number line the circle at 5 is __B1__ (open / closed).", "a": {"B1": "closed"}, "expr": "words", "accept": ["filled", "shaded", "solid"]}], "sol": "11 + 4 = 15.\n15 ÷ 3 = 5.\n≥ includes 5, so the circle is closed."}, {"kind": "blank", "p": "Solve 7 − 2m < 1.", "tag": "", "marks": "", "flat": [{"t": "Subtract 7: −2m < __B1__", "a": {"B1": "-6"}}, {"t": "Divide by −2 and reverse the sign: m __B1__ 3", "a": {"B1": ">"}}, {"t": "The arrow on the number line points __B1__.", "a": {"B1": "right"}, "expr": "words"}], "sol": "1 − 7 = −6.\n−6 ÷ (−2) = 3, and < becomes >: m > 3.\nGreater than: to the right."}, {"kind": "blank", "p": "Solve 4(p + 2) ≤ 2p − 6.", "tag": "", "marks": "", "flat": [{"t": "Expand: __B1__ ≤ 2p − 6", "a": {"B1": "4p+8"}, "expr": true}, {"t": "Subtract 2p and 8: 2p ≤ __B1__", "a": {"B1": "-14"}}, {"t": "p ≤ __B1__", "a": {"B1": "-7"}}], "sol": "4p + 8.\n−6 − 8 = −14.\n−14 ÷ 2 = −7 (dividing by a positive, so no change)."}, {"kind": "blank", "p": "Look at the number line.", "tag": "", "marks": "", "flat": [{"t": "The inequality is x __B1__ −4", "a": {"B1": ">"}}, {"t": "The smallest integer that satisfies it is __B1__.", "a": {"B1": "-3"}}], "sol": "Open circle at −4 and arrow right: x > −4.\n−4 is not included, so the smallest integer is −3.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 62\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line class=\"ln\" x1=\"8.0\" y1=\"28.0\" x2=\"312.0\" y2=\"28.0\"/><line x1=\"22.0\" y1=\"23\" x2=\"22.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"22.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−8</text><line x1=\"49.6\" y1=\"23\" x2=\"49.6\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"49.6\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−7</text><line x1=\"77.2\" y1=\"23\" x2=\"77.2\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"77.2\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><line x1=\"104.8\" y1=\"23\" x2=\"104.8\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"104.8\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−5</text><line x1=\"132.4\" y1=\"23\" x2=\"132.4\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"132.4\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><line x1=\"160.0\" y1=\"23\" x2=\"160.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"160.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−3</text><line x1=\"187.6\" y1=\"23\" x2=\"187.6\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"187.6\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><line x1=\"215.2\" y1=\"23\" x2=\"215.2\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"215.2\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><line x1=\"242.8\" y1=\"23\" x2=\"242.8\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"242.8\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"270.4\" y1=\"23\" x2=\"270.4\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"270.4\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"298.0\" y1=\"23\" x2=\"298.0\" y2=\"33\" style=\"stroke:var(--ink);stroke-width:1.1\"/><text class=\"po\" x=\"298.0\" y=\"45.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"132.4\" y1=\"28\" x2=\"304.0\" y2=\"28\" style=\"stroke:var(--accent-text);stroke-width:4;stroke-linecap:round\"/><path d=\"M312.0,28 L302.0,22 L302.0,34 Z\" style=\"fill:var(--accent-text)\"/><circle cx=\"132.4\" cy=\"28\" r=\"5.5\" style=\"fill:var(--card);stroke:var(--accent-text);stroke-width:2.2\"/></svg>"}, {"kind": "blank", "p": "A number n is more than 20 and at most 25.", "tag": "", "marks": "", "flat": [{"t": "20 __B1__ n", "a": {"B1": "<"}}, {"t": "n __B1__ 25", "a": {"B1": "≤"}, "accept": ["<=", "=<"]}, {"t": "The number of integers n could be is __B1__.", "a": {"B1": "5"}}], "sol": "More than 20: 20 < n.\nAt most 25: n ≤ 25.\n21, 22, 23, 24, 25: five integers."}]}, {"id": "s7", "label": "Test A", "sub": "Criterion A — Knowing and understanding", "slides": [{"kind": "mcq", "text": "How is 6x²y³ − xy + 4 classified?", "opts": ["a trinomial of degree 6", "a trinomial of degree 5", "a trinomial of degree 3", "a binomial of degree 5"], "correct": 1, "tag": "", "sol": "Three terms; degrees 2 + 3 = 5, 2 and 0, so degree 5."}, {"kind": "mcq", "text": "Simplify 9p − 4q − 2p + 7q.", "opts": ["10pq", "7p + 3q", "7p − 11q", "11p + 3q"], "correct": 1, "tag": "", "sol": "9p − 2p = 7p and −4q + 7q = 3q."}, {"kind": "mcq", "text": "Expand and simplify 2(5c − 1) − (c + 4).", "opts": ["9c + 2", "9c − 6", "9c − 2", "11c − 6"], "correct": 1, "tag": "", "sol": "10c − 2 − c − 4 = 9c − 6."}, {"kind": "mcq", "text": "Solve 6x − 11 = 2x + 9.", "opts": ["x = 0.5", "x = 5", "x = 2.5", "x = −5"], "correct": 1, "tag": "", "sol": "4x − 11 = 9, 4x = 20, x = 5."}, {"kind": "mcq", "text": "Solve h/3 + 7 = 2.", "opts": ["h = −{5/3}", "h = −15", "h = 15", "h = 27"], "correct": 1, "tag": "", "sol": "h/3 = −5, so h = −15."}, {"kind": "mcq", "text": "Solve −4z < 20.", "opts": ["z > 5", "z < −5", "z < 5", "z > −5"], "correct": 3, "tag": "", "sol": "Divide by −4 and reverse the sign: z > −5."}, {"kind": "mcq", "text": "What is the inverse of y = 2x − 8?", "opts": ["y = x/2 + 4", "y = 2x + 8", "y = x/2 − 4", "y = (x − 8)/2"], "correct": 0, "tag": "", "sol": "Swap: x = 2y − 8, so 2y = x + 8 and y = (x + 8)/2 = x/2 + 4."}, {"kind": "mcq", "text": "Write “five less than the product of 3 and a number n”.", "opts": ["3(n − 5)", "3 + n − 5", "5 − 3n", "3n − 5"], "correct": 3, "tag": "", "sol": "The product of 3 and n is 3n; five less is 3n − 5."}, {"kind": "blank", "p": "Write 8 − 5a³ + a − 2a² in standard form.", "tag": "", "marks": "", "flat": [{"t": "Standard form: __B1__", "a": {"B1": "-5a^3-2a^2+a+8"}, "expr": true}, {"t": "Degree = __B1__", "a": {"B1": "3"}}, {"t": "By degree it is __B1__.", "a": {"B1": "cubic"}, "expr": "words"}], "sol": "Descending powers: −5a³ − 2a² + a + 8.\nHighest power 3.\nDegree 3 is cubic."}, {"kind": "blank", "p": "Solve 5(2e − 3) = 3(e + 2).", "tag": "", "marks": "", "flat": [{"t": "Expand: __B1__ = 3e + 6", "a": {"B1": "10e-15"}, "expr": true}, {"t": "7e = __B1__", "a": {"B1": "21"}}, {"t": "e = __B1__", "a": {"B1": "3"}}], "sol": "10e − 15.\nSubtract 3e and add 15: 7e = 21.\ne = 3. Check: 5 × 3 = 15 and 3 × 5 = 15 ✓"}, {"kind": "blank", "p": "Solve 3 − 4u ≥ 23.", "tag": "", "marks": "", "flat": [{"t": "Subtract 3: −4u ≥ __B1__", "a": {"B1": "20"}}, {"t": "Divide by −4: u __B1__ −5", "a": {"B1": "≤"}, "accept": ["<=", "=<"]}], "sol": "23 − 3 = 20.\nDividing by a negative reverses ≥ to ≤: u ≤ −5."}, {"kind": "blank", "p": "Simplify 3x² − 5x + 8 − x² + 2x − 3, then evaluate it.", "tag": "", "marks": "", "flat": [{"t": "Simplified: __B1__", "a": {"B1": "2x^2-3x+5"}, "expr": true}, {"t": "Value when x = 2: __B1__", "a": {"B1": "7"}}], "sol": "3x² − x² = 2x², −5x + 2x = −3x, 8 − 3 = 5.\n2 × 4 − 3 × 2 + 5 = 8 − 6 + 5 = 7."}]}, {"id": "s8", "label": "Test B", "sub": "Criterion B — Investigating patterns", "slides": [{"kind": "mcq", "text": "The sums of three consecutive integers are 6 (1 + 2 + 3), 9, 12, 15, … Which rule is always true?", "opts": ["The sum is always a multiple of 3", "The sum is always odd", "The sum is always a multiple of 6", "The sum is always even"], "correct": 0, "tag": "", "sol": "n + (n + 1) + (n + 2) = 3n + 3 = 3(n + 1), a multiple of 3. 9 and 15 are odd, so it is not always even or a multiple of 6."}, {"kind": "mcq", "text": "Start with 8 > 2. Multiply both sides by 2: 16 > 4. Multiply both sides by 5: 40 > 10. Now multiply by −1, −2 and −3: −8 < −2, −16 < −4, −24 < −6. Which rule fits all of these results?", "opts": ["The sign reverses when you multiply by any number", "Only multiplying by −1 changes the sign", "Multiplying by a negative number reverses the inequality sign", "Multiplying never changes the sign"], "correct": 2, "tag": "", "sol": "Multiplying by 2 or 5 keeps >, but multiplying by −1, −2 or −3 turns > into <. So the sign reverses exactly when the multiplier is negative."}, {"kind": "mcq", "text": "The polynomials 1 + x, 1 + x + x², 1 + x + x² + x³, … continue. Describe the 10th polynomial.", "opts": ["degree 9 with 10 terms", "degree 10 with 10 terms", "degree 11 with 11 terms", "degree 10 with 11 terms"], "correct": 3, "tag": "", "sol": "The nth polynomial is 1 + x + … + xⁿ: degree n with n + 1 terms. For n = 10: degree 10, 11 terms."}, {"kind": "mcq", "text": "A trick says: double your number, add 9, subtract 3, halve it, then subtract your number. The answer is always 3. Which working proves it?", "opts": ["(2n + 6) ÷ 2 = n + 6", "2n + 9 − 3 − n = n + 6", "2 × 5 + 9 − 3 = 16, 16 ÷ 2 − 5 = 3", "(2n + 9 − 3) ÷ 2 − n = n + 3 − n = 3"], "correct": 3, "tag": "", "sol": "Only algebra with a general n proves it for every number. One example (n = 5) does not prove a rule."}, {"kind": "mcq", "text": "The pattern 3, 7, 11, 15, … continues. Which expression gives the nth term, and is 101 in the pattern?", "opts": ["n + 4; yes, it is term 97", "4n − 1; no, because 4n − 1 = 101 gives n = 25.5", "4n + 3; no", "4n − 1; yes, it is term 25"], "correct": 1, "tag": "", "sol": "The terms go up by 4 and the first is 3 = 4 × 1 − 1, so 4n − 1. 4n = 102 gives n = 25.5, not a whole number, so 101 is not a term."}, {"kind": "blank", "p": "Investigate 2 × 2 blocks on a calendar: multiply the diagonal corners and find the difference.", "tag": "", "marks": "", "flat": [{"t": "Block 3, 4, 10, 11: 3 × 11 = __B1__ and 4 × 10 = __B2__", "a": {"B1": "33", "B2": "40"}}, {"t": "Block 9, 10, 16, 17: 9 × 17 = __B1__ and 10 × 16 = __B2__", "a": {"B1": "153", "B2": "160"}}, {"t": "General block n, n + 1, n + 7, n + 8: n(n + 8) = __B1__", "a": {"B1": "n^2+8n"}, "expr": true}, {"t": "(n + 1)(n + 7) = __B1__", "a": {"B1": "n^2+8n+7"}, "expr": true}, {"t": "So the difference is always __B1__.", "a": {"B1": "7"}}], "sol": "33 and 40: difference 7.\n153 and 160: difference 7.\nn² + 8n.\nn² + 7n + n + 7 = n² + 8n + 7.\n(n² + 8n + 7) − (n² + 8n) = 7 for every block."}, {"kind": "blank", "p": "Investigate the sum of five consecutive integers.", "tag": "", "marks": "", "flat": [{"t": "1 + 2 + 3 + 4 + 5 = __B1__", "a": {"B1": "15"}}, {"t": "4 + 5 + 6 + 7 + 8 = __B1__", "a": {"B1": "30"}}, {"t": "10 + 11 + 12 + 13 + 14 = __B1__", "a": {"B1": "60"}}, {"t": "With middle number m, the integers are m − 2, …, m + 2 and the sum is __B1__", "a": {"B1": "5m"}, "expr": true}, {"t": "Can five consecutive integers add up to 83? __B1__", "a": {"B1": "no"}, "expr": "words", "accept": ["n"]}], "sol": "15 = 5 × 3.\n30 = 5 × 6.\n60 = 5 × 12.\n(m − 2) + (m − 1) + m + (m + 1) + (m + 2) = 5m.\nThe sum is always a multiple of 5, and 83 is not."}, {"kind": "blank", "p": "Investigate adding, subtracting and dividing both sides of the true inequality −6 < 9.", "tag": "", "marks": "", "flat": [{"t": "Add 4 to both sides: −2 __B1__ 13", "a": {"B1": "<"}}, {"t": "Subtract 10 from both sides: −16 __B1__ −1", "a": {"B1": "<"}}, {"t": "Divide both sides by 3: −2 __B1__ 3", "a": {"B1": "<"}}, {"t": "Divide both sides by −3: 2 __B1__ −3", "a": {"B1": ">"}}, {"t": "Rule: adding or subtracting never changes the sign, but dividing by a negative number means the sign must be __B1__.", "a": {"B1": "reversed"}, "expr": "words", "accept": ["reverses", "reverse", "flipped", "flip", "flips", "switched", "swapped", "changed", "opposite", "inverted", "turned around", "turnedaround"]}], "sol": "−6 + 4 = −2 and 9 + 4 = 13: still <.\n−6 − 10 = −16 and 9 − 10 = −1: still <.\n−6 ÷ 3 = −2 and 9 ÷ 3 = 3: still <.\n−6 ÷ (−3) = 2 and 9 ÷ (−3) = −3, and 2 > −3: the sign has turned round.\nAdding, subtracting or dividing by a positive keeps the sign; dividing by a negative reverses it."}, {"kind": "blank", "p": "Investigate adding a two-digit number to its reverse.", "tag": "", "marks": "", "flat": [{"t": "23 + 32 = __B1__", "a": {"B1": "55"}}, {"t": "47 + 74 = __B1__", "a": {"B1": "121"}}, {"t": "General: (10a + b) + (10b + a) = __B1__", "a": {"B1": "11a+11b"}, "expr": true}, {"t": "So the sum is always a multiple of __B1__.", "a": {"B1": "11"}}], "sol": "55 = 11 × 5.\n121 = 11 × 11.\n11a + 11b = 11(a + b).\nIt is 11 × (sum of the digits), so always a multiple of 11."}]}, {"id": "s9", "label": "Test C", "sub": "Criterion C — Communicating", "slides": [{"kind": "mcq", "text": "A student writes: “3x²y + 5xy − 2 is a trinomial of degree 2, because the biggest exponent is 2.” What is wrong with the explanation?", "opts": ["Its degree is 2 + 1 + 1 + 1 = 5", "Nothing is wrong", "The degree of 3x²y is 2 + 1 = 3, so it is a trinomial of degree 3", "It has two terms, so it is a binomial"], "correct": 2, "tag": "", "sol": "The degree of a term is the sum of the exponents of its variables: x²y has degree 3. The terms have degrees 3, 2 and 0, so the polynomial has degree 3."}, {"kind": "mcq", "text": "A student writes 5 − 2(x + 3) = 5 − 2x + 6 = 11 − 2x. What is the mistake?", "opts": ["−2 × 3 is −6, so it should be 5 − 2x − 6 = −1 − 2x", "5 − 2 should be done first", "There is no mistake", "The x term should be +2x"], "correct": 0, "tag": "", "sol": "The −2 multiplies both terms in the bracket: −2 × x = −2x and −2 × 3 = −6."}, {"kind": "mcq", "text": "A student solves −3x > 12 and writes x > −4. What is wrong?", "opts": ["The answer should be x > 4", "12 ÷ −3 is 4, not −4", "Nothing is wrong", "Dividing by −3 should reverse the sign: x < −4"], "correct": 3, "tag": "", "sol": "Dividing both sides by a negative number reverses the inequality: x < −4. Check: x = 0 gives 0 > 12, false, so x > −4 cannot be right."}, {"kind": "mcq", "text": "Which uses correct notation for “the number n is at least 4 and less than 9”?", "opts": ["4 ≥ n > 9", "n ≤ 4 < 9", "4 ≤ n < 9", "4 < n ≤ 9"], "correct": 2, "tag": "", "sol": "“At least 4” includes 4 (≤ from the left) and “less than 9” excludes 9 (<). A double inequality is read from the variable outwards: 4 ≤ n and n < 9."}, {"kind": "mcq", "text": "Which number line matches “x is at most 6”?", "opts": ["Open circle at 6, arrow to the left", "Closed circle at 6, arrow to the right", "Closed circle at 6, arrow to the left", "Open circle at 6, arrow to the right"], "correct": 2, "tag": "", "sol": "“At most 6” means x ≤ 6: 6 is included (closed) and smaller numbers are to the left."}, {"kind": "mcq", "text": "Which is the best justification that the sum of two odd numbers is always even?", "opts": ["3 + 5 = 8 and 7 + 9 = 16, so it always works", "2n + 1 + 2n + 1 = 4n + 2 for all odd numbers", "(2m + 1) + (2n + 1) = 2m + 2n + 2 = 2(m + n + 1), which is 2 × a whole number", "Odd plus odd makes even because they cancel"], "correct": 2, "tag": "", "sol": "General odd numbers need different letters (2m + 1 and 2n + 1); the result is a multiple of 2. Examples alone do not prove it, and using n twice only covers equal numbers."}, {"kind": "mcq", "text": "A garden's width w satisfies 2w + 2(w + 4) = 48, so w = 10. Which is the clearest final answer?", "opts": ["10", "The garden is 10 m wide and 14 m long.", "The garden is 10 m².", "w = 10"], "correct": 1, "tag": "", "sol": "Answer the question in a sentence, with units, and give both dimensions: w + 4 = 14 m. m² is a unit of area, not length."}, {"kind": "mcq", "text": "A student solves 4x + 7 = 2x − 5 by writing 6x = −12, so x = −2. What is the mistake?", "opts": ["7 should be added to both sides", "−12 ÷ 6 is not −2", "There is no mistake", "2x should be subtracted, not added: 2x = −12, so x = −6"], "correct": 3, "tag": "", "sol": "To remove 2x from the right, subtract 2x from both sides: 2x + 7 = −5, 2x = −12, x = −6. Check: 4(−6) + 7 = −17 and 2(−6) − 5 = −17 ✓"}, {"kind": "blank", "p": "Complete the explanation of how to solve 3x + 4 = 19.", "tag": "", "marks": "", "flat": [{"t": "First subtract __B1__ from both sides", "a": {"B1": "4"}}, {"t": "so that the equation stays __B1__.", "a": {"B1": "balanced"}, "expr": "words", "accept": ["equal", "true", "balance", "the same"]}, {"t": "Then divide both sides by __B1__ to get x = 5.", "a": {"B1": "3"}}], "sol": "Subtract 4: 3x = 15.\nDoing the same to both sides keeps the balance level (the equation true).\n15 ÷ 3 = 5."}, {"kind": "blank", "p": "Complete the description of x > −3.", "tag": "", "marks": "", "flat": [{"t": "In words: x is __B1__ than −3.", "a": {"B1": "greater"}, "expr": "words", "accept": ["more", "bigger", "larger"]}, {"t": "On a number line use an __B1__ circle at −3", "a": {"B1": "open"}, "expr": "words", "accept": ["empty", "hollow", "unfilled", "unshaded"]}, {"t": "with the arrow pointing to the __B1__.", "a": {"B1": "right"}, "expr": "words"}], "sol": "> means “greater than”.\n−3 itself is not included, so the circle is open.\nGreater numbers are to the right."}]}, {"id": "s10", "label": "Test D", "sub": "Criterion D — Applying mathematics in real-life contexts", "slides": [{"kind": "mcq", "text": "A phone plan costs ₹199 a month plus ₹2 per minute of international calls. Neha's bill is ₹345. How many international minutes did she use?", "opts": ["172.5", "72", "146", "73"], "correct": 3, "tag": "", "sol": "199 + 2m = 345, so 2m = 146 and m = 73."}, {"kind": "mcq", "text": "A cab charges ₹50 plus ₹14 per km. Arjun has ₹400. What is the greatest whole number of km he can travel?", "opts": ["24 km", "32 km", "25 km", "28 km"], "correct": 2, "tag": "", "sol": "50 + 14d ≤ 400, so 14d ≤ 350 and d ≤ 25."}, {"kind": "mcq", "text": "Data plan A costs ₹300 plus ₹5 per GB; plan B costs ₹180 plus ₹9 per GB. For how many GB do the plans cost the same?", "opts": ["120 GB", "30 GB", "20 GB", "15 GB"], "correct": 1, "tag": "", "sol": "300 + 5g = 180 + 9g, so 120 = 4g and g = 30. (Both cost ₹450.)"}, {"kind": "mcq", "text": "Meera is 3 times as old as her son. In 12 years she will be twice as old as him. A student claims the son is 30 now. Is this reasonable?", "opts": ["No: 3s + 12 = 2(s + 12) gives s = 12, and s = 30 would make Meera 90", "Yes: the son must be older than 12", "Yes: 30 × 3 = 90", "No: the son must be 24"], "correct": 0, "tag": "", "sol": "3s + 12 = 2s + 24, so s = 12 (Meera 36; in 12 years 48 = 2 × 24 ✓). With s = 30, 102 ≠ 84, and a 90-year-old mother is unlikely anyway."}, {"kind": "mcq", "text": "A school hall can hold at most 450 people. 30 staff will stand, and 12 equal rows of chairs are set out. What is the greatest number of chairs in each row?", "opts": ["36", "40", "37", "35"], "correct": 3, "tag": "", "sol": "12c + 30 ≤ 450, so 12c ≤ 420 and c ≤ 35. (37 forgets the standing staff; 40 adds the 30 instead of subtracting it.)"}, {"kind": "mcq", "text": "A Diwali stall sells laddoos at ₹15 each. Its costs are ₹600 to set up plus ₹6 per laddoo. What is the smallest number of laddoos it must sell to make a profit?", "opts": ["66", "40", "67", "100"], "correct": 2, "tag": "", "sol": "15n > 600 + 6n, so 9n > 600 and n > 66.7. The smallest whole number is 67."}, {"kind": "blank", "p": "A school trip costs ₹4500 for the bus plus ₹250 per student for entry tickets. The budget is ₹14 500. Let s be the number of students.", "tag": "", "marks": "", "flat": [{"t": "4500 + 250s __B1__ 14 500", "a": {"B1": "≤"}, "accept": ["<=", "=<"]}, {"t": "250s ≤ __B1__", "a": {"B1": "10000"}}, {"t": "The greatest number of students is __B1__.", "a": {"B1": "40"}}], "sol": "The cost must be no more than the budget: ≤.\n14 500 − 4500 = 10 000.\n10 000 ÷ 250 = 40."}, {"kind": "blank", "p": "A rectangular vegetable garden is 5 m longer than it is wide. It needs 46 m of fencing all round. Let the width be w m.", "tag": "", "marks": "", "flat": [{"t": "Perimeter = __B1__", "a": {"B1": "4w+10"}, "expr": true}, {"t": "w = __B1__ m", "a": {"B1": "9"}}, {"t": "Length = __B1__ m", "a": {"B1": "14"}}, {"t": "Area = __B1__ m²", "a": {"B1": "126"}}], "sol": "2w + 2(w + 5) = 4w + 10.\n4w + 10 = 46, 4w = 36, w = 9.\n9 + 5 = 14.\n9 × 14 = 126."}, {"kind": "blank", "p": "Ananya has ₹1200 and saves ₹150 a week. Kabir has ₹2100 and saves ₹75 a week. After w weeks they have the same amount.", "tag": "", "marks": "", "flat": [{"t": "Equation: 1200 + 150w = __B1__", "a": {"B1": "2100+75w"}, "expr": true}, {"t": "w = __B1__", "a": {"B1": "12"}}, {"t": "They will each have ₹__B1__.", "a": {"B1": "3000"}}], "sol": "Kabir's savings after w weeks: 2100 + 75w.\n75w = 900, w = 12.\n1200 + 150 × 12 = 3000 (and 2100 + 75 × 12 = 3000 ✓)."}, {"kind": "blank", "p": "Temperature in °F is F = 1.8C + 32, where C is in °C.", "tag": "", "marks": "", "flat": [{"t": "The inverse function is C = __B1__", "a": {"B1": "(F-32)/1.8"}, "expr": true}, {"t": "A body temperature of 98.6 °F is __B1__ °C.", "a": {"B1": "37"}}, {"t": "A student says 212 °F is 212 ÷ 1.8 ≈ 118 °C. The correct value is __B1__ °C.", "a": {"B1": "100"}}], "sol": "F − 32 = 1.8C, so C = (F − 32)/1.8.\n(98.6 − 32) ÷ 1.8 = 66.6 ÷ 1.8 = 37.\n(212 − 32) ÷ 1.8 = 100 °C, the boiling point of water; the student forgot to subtract 32 first."}]}];
/* ================= build slide lists ================= */
var SLIDES = {}; SECTIONS.forEach(function(sec){ SLIDES[sec.id]=sec.slides; });
var TAB_DEFS = SECTIONS.map(function(sec){ return {id:sec.id, label:sec.label, sub:sec.sub}; });

/* ================= state ================= */
function blankItem(slide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    return {status:'unanswered', attempts:0, choice:undefined};
  }
  return {status:'unanswered', curStep:0, stepStates: slide.flat.map(function(){ return {status:'unanswered', attempts:0, inputs:{}}; })};
}
function defaultState(){
  var s={tabs:{}};
  TAB_DEFS.forEach(function(td){
    s.tabs[td.id] = { idx:0, maxReached:0, items: SLIDES[td.id].map(function(sl){ return blankItem(sl); }) };
  });
  return s;
}
var appState = {mode:null, learning:null, quiz:null};
var state = null;      // alias for appState[appState.mode]
var MODE = null;
var activeTab=TAB_DEFS[0].id;

function setMode(m){
  appState.mode = m;
  if(!appState[m]) appState[m] = defaultState();
  state = appState[m];
  MODE = m;
}
/* ================= student accounts (saved on this device) ================= */
var SHEET_KEY='sopaan-myp2-u4';
var ACC_KEY='sopaan-students-v1';
var storageOK=true;
var MEM={};
function lsGet(k){ var r=null; try{ r=localStorage.getItem(k); }catch(e){ storageOK=false; }
  if(r===null||r===undefined) r=MEM[k]||null; try{ return r?JSON.parse(r):null; }catch(e){ return null; } }
function lsSet(k,v){ var j=JSON.stringify(v); MEM[k]=j; try{ localStorage.setItem(k,j); return true; }catch(e){ storageOK=false; return false; } }
try{ localStorage.setItem('sopaan-probe','1'); localStorage.removeItem('sopaan-probe'); }catch(e){ storageOK=false; }
function hashPin(pin,salt){ var h=2166136261, str=salt+'|'+pin; for(var i=0;i<str.length;i++){ h^=str.charCodeAt(i); h=Math.imul(h,16777619)>>>0; } return h.toString(36); }
function accKey(name,roll){ return (name.trim().toLowerCase().replace(/\s+/g,' ')+'#'+roll.trim().toLowerCase()); }
function accounts(){ return lsGet(ACC_KEY)||{students:{}}; }
var student=null; // {key,name,roll}
var records=[];   // finished-tab history for this student on this sheet
function progKey(){ return SHEET_KEY+'::'+student.key; }

function loadState(){
  appState = {mode:null, learning:null, quiz:null}; records=[]; activeTab=TAB_DEFS[0].id;
  var saved=lsGet(progKey());
  if(!saved) return;
  try{
    ['learning','quiz'].forEach(function(m){
      if(saved[m] && saved[m].tabs){
        var fresh = defaultState();
        TAB_DEFS.forEach(function(td){
          if(saved[m].tabs[td.id] && saved[m].tabs[td.id].items && saved[m].tabs[td.id].items.length===SLIDES[td.id].length){
            fresh.tabs[td.id] = saved[m].tabs[td.id];
          }
        });
        appState[m] = fresh;
      }
    });
    if(saved.mode==='learning' || saved.mode==='quiz') appState.mode = saved.mode;
    if(saved.activeTab && TAB_DEFS.some(function(t){ return t.id===saved.activeTab; })) activeTab = saved.activeTab;
    if(Array.isArray(saved.records)) records = saved.records;
  }catch(e){}
}
function saveState(){
  if(!student) return;
  lsSet(progKey(), {mode:appState.mode, learning:appState.learning, quiz:appState.quiz, activeTab:activeTab, records:records, updated:Date.now()});
  var acc=accounts(); if(acc.students[student.key]){ acc.students[student.key].last=Date.now(); lsSet(ACC_KEY,acc); }
}
function addRecord(mode, tabId, correct, revealed, skipped, total){
  records.unshift({at:Date.now(), mode:mode, tab:tabId, correct:correct, revealed:revealed, skipped:skipped, total:total});
  if(records.length>60) records.length=60;
  saveState();
}
function fmtDate(ms){ try{ return new Date(ms).toLocaleString(undefined,{day:'numeric',month:'short',hour:'2-digit',minute:'2-digit'}); }catch(e){ return ''; } }

function renderWho(){
  var el=document.getElementById('whoBar');
  if(!student){ el.hidden=true; el.innerHTML=''; return; }
  el.hidden=false;
  el.innerHTML='Signed in as <b>'+esc(student.name)+'</b> · Roll '+esc(student.roll)+
    ' <button id="btnRecord">My record</button> <button id="btnSignOut">Sign out</button>';
  document.getElementById('btnRecord').addEventListener('click', renderRecord);
  document.getElementById('btnSignOut').addEventListener('click', signOut);
}
function signOut(){
  saveState(); student=null; state=null; MODE=null;
  var acc=accounts(); delete acc.current; lsSet(ACC_KEY,acc);
  document.getElementById('modePill').hidden=true;
  renderWho(); renderLogin();
}
function signIn(key){
  var acc=accounts(); var st=acc.students[key]; if(!st) return;
  student={key:key, name:st.name, roll:st.roll};
  acc.current=key; st.last=Date.now(); lsSet(ACC_KEY,acc);
  loadState(); renderWho();
  if(appState.mode==='learning' || appState.mode==='quiz'){
    setMode(appState.mode); document.getElementById('modePill').hidden=false; updateModePill();
    showChrome(true); buildTabbar(); renderSlide();
    showToast('Welcome back, '+st.name.split(' ')[0]+'. Picking up where you left off.');
  } else {
    renderModePicker();
  }
}
function renderLogin(msg){
  showChrome(false);
  var acc=accounts(); var keys=Object.keys(acc.students).sort(function(a,b){ return (acc.students[b].last||0)-(acc.students[a].last||0); });
  var h='<div class="login-card"><h2>Student sign-in</h2>'+
    '<p class="lead">Sign in to save your answers, see your record and continue where you left off next time.</p>';
  if(!storageOK) h+='<div class="login-err">This browser is blocking saved data (for example, a private window). You can still practise, but progress will not be kept after you close the page.</div>';
  if(msg) h+='<div class="login-err">'+esc(msg)+'</div>';
  if(keys.length){
    h+='<div class="known"><span class="known-label">Continue as</span>';
    keys.slice(0,6).forEach(function(k){ var st=acc.students[k];
      h+='<button class="known-btn" data-k="'+esc(k)+'"><span>'+esc(st.name)+' <small>· Roll '+esc(st.roll)+'</small></span><small>'+(st.last?'Last active '+fmtDate(st.last):'')+'</small></button>'; });
    h+='</div>';
  }
  h+='<form id="loginForm" novalidate>'+
    '<div class="fld"><label for="lgName">Full name</label><input id="lgName" autocomplete="name" required></div>'+
    '<div class="fld-row"><div class="fld"><label for="lgRoll">Roll no.</label><input id="lgRoll" required></div>'+
    '<div class="fld"><label for="lgPin">4-digit PIN</label><input id="lgPin" type="password" inputmode="numeric" maxlength="4" autocomplete="off" required></div></div>'+
    '<button class="btn btn-primary" type="submit" style="width:100%;">Sign in</button>'+
    '<p class="login-note">New here? Enter your name, roll no. and a PIN you will remember, and your profile is created. Progress is saved on this device, so use the same device and browser to continue.</p>'+
    '</form></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  wrap.querySelectorAll('.known-btn').forEach(function(b){
    b.addEventListener('click', function(){
      var st=accounts().students[b.dataset.k];
      document.getElementById('lgName').value=st.name; document.getElementById('lgRoll').value=st.roll;
      document.getElementById('lgPin').focus();
    });
  });
  document.getElementById('loginForm').addEventListener('submit', function(e){
    e.preventDefault();
    var name=document.getElementById('lgName').value.trim(), roll=document.getElementById('lgRoll').value.trim(), pin=document.getElementById('lgPin').value.trim();
    if(!name||!roll){ renderLoginErr('Enter your name and roll no.'); return; }
    if(!/^\d{4}$/.test(pin)){ renderLoginErr('Your PIN must be exactly 4 digits.'); return; }
    var k=accKey(name,roll); var acc=accounts();
    if(acc.students[k]){
      if(acc.students[k].pin!==hashPin(pin,k)){ renderLoginErr('That PIN does not match this name and roll no. Try again.'); return; }
    } else {
      acc.students[k]={name:name.replace(/\s+/g,' '), roll:roll, pin:hashPin(pin,k), created:Date.now()};
      lsSet(ACC_KEY,acc);
    }
    signIn(k);
  });
}
function renderLoginErr(m){
  var n=document.getElementById('lgName').value, r=document.getElementById('lgRoll').value;
  renderLogin(m); document.getElementById('lgName').value=n; document.getElementById('lgRoll').value=r; document.getElementById('lgPin').focus();
}
function tabSummary(m){
  var st=appState[m]; if(!st) return null;
  return TAB_DEFS.map(function(td){
    var items=st.tabs[td.id].items, n=items.length;
    var c=items.filter(function(i){return i.status==='correct';}).length;
    var done=items.filter(function(i){return i.status!=='unanswered';}).length;
    return {label:td.label, n:n, done:done, correct:c};
  });
}
function renderRecord(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+' · Algebraic expressions and equations</p>';
  ['learning','quiz'].forEach(function(m){
    var sum=tabSummary(m);
    h+='<h3>'+(m==='learning'?'📘 Learning Sheet':'📝 Quiz Mode')+'</h3>';
    if(!sum){ h+='<p class="rec-empty">Not started yet.</p>'; return; }
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>Section</th><th>Progress</th><th>Correct first time</th></tr></thead><tbody>';
    sum.forEach(function(r){ var pct=Math.round(r.done/r.n*100);
      h+='<tr><td>'+r.label+'</td><td><span class="rec-bar"><i style="width:'+pct+'%"></i></span>'+r.done+' / '+r.n+'</td><td>'+(m==='quiz'?'—':r.correct+' / '+r.n)+'</td></tr>'; });
    h+='</tbody></table></div>';
  });
  h+='</div><div class="rec-card"><h3>Finished sections</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sections finished yet. Each time you finish a tab, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>When</th><th>Mode</th><th>Section</th><th>Score</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+(r.mode==='learning'?' <span class="rec-empty">('+r.revealed+' revealed, '+r.skipped+' skipped)</span>':'')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){
    if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker();
  });
  window.scrollTo({top:0});
}

/* ================= tab bar ================= */
function buildTabbar(){
  var el=document.getElementById('tabbar');
  el.innerHTML = '<button class="tab-btn'+(activeTab==='theory'?' active':'')+'" data-tab="theory">Theory<span class="tab-count">notes</span></button>' + TAB_DEFS.map(function(t){
    return '<button class="tab-btn'+(t.id===activeTab?' active':'')+'" data-tab="'+t.id+'">'+t.label+'<span class="tab-count">'+SLIDES[t.id].length+'</span></button>';
  }).join('') + '<button class="tab-btn'+(activeTab==='report'?' active':'')+'" data-tab="report">📊 Report<span class="tab-count">pie</span></button>';
  el.querySelectorAll('.tab-btn').forEach(function(btn){
    btn.addEventListener('click', function(){ activeTab=btn.dataset.tab; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  });
}

/* ================= rendering ================= */
function canProceed(item){ return item.status==='correct'||item.status==='revealed'||item.status==='skipped'; }

function renderSlide(){
  if(!state.tabs[activeTab]){ activeTab=TAB_DEFS[0].id; }
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  if(ts.idx>=slides.length||ts.idx<0) ts.idx=0;
  var idx = ts.idx;
  var slide = slides[idx];
  var item = ts.items[idx];

  var tdef=TAB_DEFS.find(function(t){return t.id===activeTab;});
  document.getElementById('spLabel').textContent = tdef.label+' · Question '+(idx+1)+' of '+slides.length;
  document.getElementById('secSub').textContent = tdef.label+' — '+tdef.sub;
  document.getElementById('spFill').style.width = Math.round(((idx)/(Math.max(slides.length-1,1)))*100)+'%';

  var h='<div class="qcard">';
  if(slide.kind==='mcq' || slide.kind==='ar'){
    h += renderChoiceBody(slide, item, idx);
  } else {
    h += renderBlankBody(slide, item, idx);
  }
  h += '<div class="feedback" id="feedbackBox"></div>';
  if(MODE==='learning' && (item.status==='correct'||item.status==='revealed')) h += solutionHTML(slide);
  h += '</div>';

  document.getElementById('wrap').innerHTML = h;
  wireSlideEvents(slide, item, idx);
  restoreFeedback(item);
  renderNavbar(item);
  updateFab();
  saveState();
}

function solutionHTML(slide){
  if(!slide.sol) return '';
  return '<div class="solution"><div class="sol-h">Solution</div>'+slide.sol.split('\n').map(function(l){ return '<div class="sol-line">'+fr(esc(l))+'</div>'; }).join('')+'</div>';
}
var LETTERS=['a','b','c','d','e','f'];
function chosenHTML(slide,item){
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(item.choice===undefined) return '';
  var ok=item.choice===slide.correct;
  var h='<div class="chosen '+(ok?'ok':'bad')+'"><b>Your answer:</b> ('+LETTERS[item.choice]+') '+fr(esc(opts[item.choice]))+(ok?' ✓':' ✗')+'</div>';
  if(!ok) h+='<div class="chosen ok"><b>Correct answer:</b> ('+LETTERS[slide.correct]+') '+fr(esc(opts[slide.correct]))+'</div>';
  return h;
}
function renderChoiceBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div>';
  if(slide.kind==='mcq'){
    h += '<div class="qtext">'+fr(esc(slide.text))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  } else {
    h += '<div class="qtext"><span class="qtag" style="margin-left:0;margin-right:6px;">A / R</span>Assertion (A): '+fr(esc(slide.a))+'<br>Reason (R): '+fr(esc(slide.r))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  }
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(MODE==='quiz') h += '<div class="quiz-hint">Quiz mode — pick an option. The correct answer is revealed once you finish this tab.</div>';
  var locked = MODE==='learning' && (item.status==='correct' || item.status==='revealed');
  h += '<div class="options">';
  opts.forEach(function(opt,i){
    var cls='opt';
    if(locked){
      if(i===slide.correct) cls+=' is-correct';
      else if(item.choice===i) cls+=' is-wrong';
      cls+=' locked';
    }
    if(item.choice===i) cls+=' is-chosen';
    h += '<label class="'+cls+'"><input type="radio" name="choice" value="'+i+'" '+(item.choice===i?'checked':'')+' '+(locked?'disabled':'')+'> <span class="opt-l">('+LETTERS[i]+')</span> <span class="opt-t">'+fr(esc(opt))+'</span>'+(item.choice===i?'<span class="opt-tag">'+(locked?(i===slide.correct?'Your answer ✓':'Your answer ✗'):'Selected')+'</span>':'')+'</label>';
  });
  h += '</div>';
  if(locked) h += chosenHTML(slide,item);
  return h;
}

function renderBlankBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div><div class="qtext">';
  if(slide.kind==='case'){ h += '<b>'+esc(slide.title)+'.</b> '+esc(slide.body); }
  else { var pp=fr(esc(slide.p)).split('\n'); h += pp[0]+pp.slice(1).map(function(x){return '<span class="datline">'+x+'</span>';}).join(''); }
  h += (slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  if(slide.marks) h += '<div class="marks-pill">'+slide.marks+'</div>';
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';

  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  var blankCount=0; slide.flat.forEach(function(s){ blankCount+=Object.keys(s.a).length; });

  if(MODE==='quiz'){
    h += '<div class="step-badge">'+blankCount+' blank'+(blankCount===1?'':'s')+' in this question</div>';
    h += '<div class="quiz-hint">Quiz mode — fill in what you can. Correct answers are revealed once you finish this tab.</div>';
    if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
    if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
    h += '<div class="steps">';
    for(var qi=0; qi<total; qi++){
      var qstep = slide.flat[qi];
      var qss = item.stepStates[qi];
      if(qstep.partLabel) h += '<div class="subpart-label">'+esc(qstep.partLabel)+'</div>';
      if(qstep.orDivider) h += '<div class="or-divider">OR</div>';
      var qline = fr(qstep.t);
      Object.keys(qstep.a).forEach(function(bkey){
        var val = qss.inputs[bkey]||'';
        var inp='<input class="blank-input'+(['fv','fe','fl','fm','fi','dec'].indexOf(qstep.expr)>=0?' fr':(qstep.expr==='flist'||qstep.expr==='dlist'||qstep.expr==='glist')?' wide':qstep.expr===true?' expr':(qstep.expr==='words'||qstep.expr==='list'||qstep.expr==='expanded'||qstep.expr==='set'||qstep.expr==='primes'||qstep.expr==='trans'||qstep.expr==='rot'?' wide':''))+'" data-step="'+qi+'" data-bkey="'+bkey+'" value="'+esc(val)+'">';
        qline = qline.replace('__'+bkey+'__', inp);
      });
      if(qstep.fig) h += '<div class="fig">'+qstep.fig+'</div>';
      h += '<div class="step-line">'+qline+'</div>';
    }
    h += '</div>';
    return h;
  }

  if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
  if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
  var locked = item.status==='correct' || item.status==='revealed';
  var upto = locked ? total-1 : item.curStep;
  h += '<div class="step-badge">Step '+(Math.min(item.curStep,total-1)+1)+' of '+total+'</div>';
  h += '<div class="steps">';
  for(var i=0;i<=upto;i++){
    var step = slide.flat[i];
    var ss = item.stepStates[i];
    if(step.partLabel) h += '<div class="subpart-label">'+esc(step.partLabel)+'</div>';
    if(step.orDivider) h += '<div class="or-divider">OR</div>';
    var resolved = ss.status==='correct' || ss.status==='revealed';
    var line = fr(step.t);
    Object.keys(step.a).forEach(function(bkey){
      var fs = ss.inputs['fs_'+bkey];
      var cls = fs==='correct'?'is-correct':(fs==='wrong'?'is-wrong':'');
      var val = ss.inputs[bkey]||'';
      var dis = resolved ? 'disabled':'';
      var inp='<input class="blank-input '+cls+(['fv','fe','fl','fm','fi','dec'].indexOf(step.expr)>=0?' fr':(step.expr==='flist'||step.expr==='dlist'||step.expr==='glist')?' wide':step.expr===true?' expr':(step.expr==='words'||step.expr==='list'||step.expr==='expanded'||step.expr==='set'||step.expr==='primes'||step.expr==='trans'||step.expr==='rot'?' wide':''))+'" data-step="'+i+'" data-bkey="'+bkey+'" value="'+esc(val)+'" '+dis+'>';
      line = line.replace('__'+bkey+'__', inp);
    });
    if(step.fig) h += '<div class="fig">'+step.fig+'</div>';
    h += '<div class="step-line'+(resolved?' resolved':'')+'">'+line+'</div>';
    if(ss.status==='revealed'){
      var reveals=[];
      Object.keys(step.a).forEach(function(bkey){ reveals.push(bkey+' = '+esc(step.a[bkey])); });
      h += '<div class="reveal-note">correct: '+reveals.join(', ')+'</div>';
    }
  }
  h += '</div>';
  return h;
}

var __flash=null;
function restoreFeedback(item){
  var fb=document.getElementById('feedbackBox'); if(!fb) return;
  if(__flash){ fb.className='feedback show '+__flash.c; fb.innerHTML=__flash.h; __flash=null; return; }
  if(MODE==='quiz'){ fb.className='feedback'; fb.innerHTML=''; return; }
  if(item.status==='correct'){ fb.className='feedback show ok'; fb.innerHTML='<b>All done — correct!</b>'; }
  else if(item.status==='revealed'){ fb.className='feedback show reveal'; fb.innerHTML='<b>Answer revealed above.</b> Move on whenever you’re ready.'; }
  else if(item.status==='skipped'){ fb.className='feedback show retry'; fb.innerHTML='Skipped — you can answer it now: fill it in and press <b>Check</b>, or come back later from the Question Palette.'; }
  else { fb.className='feedback'; fb.innerHTML=''; }
}

function slideIsAnswered(slide,item){
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return item.stepStates.some(function(ss){ return Object.keys(ss.inputs).some(function(k){ return k.indexOf('fs_')!==0 && ss.inputs[k] && String(ss.inputs[k]).trim()!==''; }); });
}
function renderNavbar(item){
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  var slide = slides[ts.idx];
  var isLast = ts.idx === slides.length-1;
  var h='';
  h += '<button class="btn" id="btnPrev" '+(ts.idx===0?'disabled':'')+'>&larr; Previous</button>';

  if(MODE==='quiz'){
    h += '<button class="btn" id="btnSkip">Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnNext">'+(isLast?'Finish':'Next →')+'</button>';
  } else {
    h += '<button class="btn" id="btnSkip" '+(item.status!=='unanswered'?'disabled':'')+'>Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnCheck" '+((item.status!=='unanswered'&&item.status!=='skipped')?'disabled':'')+'>Check</button>';
    h += '<button class="btn btn-primary" id="btnNext" '+(canProceed(item)?'':'disabled')+'>'+(isLast?'Finish':'Next →')+'</button>';
  }
  document.getElementById('navbarInner').innerHTML = h;

  document.getElementById('btnPrev').addEventListener('click', function(){ if(ts.idx>0){ ts.idx--; renderSlide(); } });

  if(MODE==='quiz'){
    document.getElementById('btnSkip').addEventListener('click', function(){
      item.status='skipped';
      advanceQuiz(ts, slides);
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      item.status = slideIsAnswered(slide,item) ? 'answered' : 'unanswered';
      advanceQuiz(ts, slides);
    });
  } else {
    document.getElementById('btnSkip').addEventListener('click', function(){
      if(item.status==='unanswered'){ item.status='skipped'; renderSlide(); }
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      if(!canProceed(item)) return;
      if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
      else { renderFinished(); }
    });
    document.getElementById('btnCheck').addEventListener('click', function(){ handleCheck(); });
  }
}
function advanceQuiz(ts, slides){
  if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
  else { renderFinished(); }
}

function wireSlideEvents(slide, item, idx){
  document.querySelectorAll('input[type="radio"][name="choice"]').forEach(function(r){
    r.addEventListener('change', function(){ item.choice=parseInt(r.value,10); saveState();
      document.querySelectorAll('.opt').forEach(function(l){ l.classList.remove('is-chosen'); var t=l.querySelector('.opt-tag'); if(t) t.remove(); });
      var lab=r.closest('.opt'); lab.classList.add('is-chosen'); var tg=document.createElement('span'); tg.className='opt-tag'; tg.textContent='Selected'; lab.appendChild(tg); });
  });
  document.querySelectorAll('.blank-input').forEach(function(inp){
    inp.addEventListener('input', function(){
      var si=parseInt(inp.dataset.step,10), bk=inp.dataset.bkey;
      item.stepStates[si].inputs[bk]=inp.value;
      saveState();
    });
  });
}

function handleCheck(){
  var ts = state.tabs[activeTab];
  var slide = SLIDES[activeTab][ts.idx];
  var item = ts.items[ts.idx];
  if(item.status==='skipped') item.status='unanswered';
  var fb = document.getElementById('feedbackBox');

  if(slide.kind==='mcq' || slide.kind==='ar'){
    if(item.choice===undefined){ fb.className='feedback show err'; fb.innerHTML='Please choose an option first.'; return; }
    var ok = item.choice===slide.correct;
    if(ok){
      item.status='correct'; playSuccess();
      fb.className='feedback show ok'; fb.innerHTML='<b>Correct!</b>';
    } else {
      item.attempts=(item.attempts||0)+1;
      if(item.attempts>=2){ item.status='revealed'; playReveal(); }
      else { playWrong(); fb.className='feedback show retry'; fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'}; }
    }
    renderSlide();
    return;
  }

  // blank / case
  var step = slide.flat[item.curStep];
  var ss = item.stepStates[item.curStep];
  var blanks = Object.keys(step.a);
  var missing = blanks.some(function(k){ return !ss.inputs[k] || String(ss.inputs[k]).trim()===''; });
  if(missing){ fb.className='feedback show err'; fb.innerHTML='Fill in every blank in this step before checking.'; return; }

  var allGood=true;
  blanks.forEach(function(k){
    var good=answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr);
    ss.inputs['fs_'+k]=good?'correct':'wrong';
    if(!good) allGood=false;
  });

  if(allGood){
    ss.status='correct'; playSuccess();
    advanceStepOrFinish(item, slide);
  } else {
    ss.attempts=(ss.attempts||0)+1;
    if(ss.attempts>=2){
      ss.status='revealed'; playReveal();
      advanceStepOrFinish(item, slide);
    } else {
      playWrong();
      fb.className='feedback show retry';
      fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'};
      renderSlide();
      return;
    }
  }
  renderSlide();
}

function advanceStepOrFinish(item, slide){
  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  if(item.curStep < total-1){
    item.curStep++;
  } else {
    var anyRevealed = item.stepStates.some(function(ss){ return ss.status==='revealed'; });
    item.status = anyRevealed ? 'revealed' : 'correct';
  }
}

/* ================= palette ================= */
var overlay=document.getElementById('overlay');
function statusOf(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  return ts.items[i].status==='unanswered' ? 'locked' : ts.items[i].status;
}
function buildPalette(){
  var slides=SLIDES[activeTab];
  document.getElementById('paletteTitle').textContent = TAB_DEFS.find(function(t){return t.id===activeTab;}).label+' · Question palette';
  var body=document.getElementById('paletteBody');
  var html='';
  for(var i=0;i<slides.length;i++){
    html += '<div class="chip" data-status="'+statusOf(activeTab,i)+'" data-idx="'+i+'">'+(i+1)+'</div>';
  }
  body.innerHTML = html;
  body.querySelectorAll('.chip').forEach(function(chip){
    chip.addEventListener('click', function(){
      var i=parseInt(chip.dataset.idx,10);
      var ts=state.tabs[activeTab];
      if(i>ts.maxReached){ showToast('Finish the earlier questions to unlock this one.'); return; }
      ts.idx=i; closePalette(); renderSlide();
    });
  });
}
function openPalette(){ buildPalette(); overlay.classList.add('show'); }
function closePalette(){ overlay.classList.remove('show'); }
var toastTimer;
function showToast(msg){
  var t=document.getElementById('toast'); t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer); toastTimer=setTimeout(function(){ t.classList.remove('show'); },2200);
}
document.getElementById('paletteFab').addEventListener('click', openPalette);
document.getElementById('paletteClose').addEventListener('click', closePalette);
overlay.addEventListener('click', function(e){ if(e.target===overlay) closePalette(); });

function updateFab(){
  var slides=SLIDES[activeTab];
  var done=state.tabs[activeTab].items.filter(function(it){ return it.status==='correct'||it.status==='revealed'||it.status==='skipped'; }).length;
  document.getElementById('fabBadge').textContent = done+'/'+slides.length;
}

/* ================= overall progress + finish ================= */
function updateChapterProgress(){
  var total=0, done=0;
  TAB_DEFS.forEach(function(td){
    state.tabs[td.id].items.forEach(function(it){
      total++;
      if(it.status==='correct'||it.status==='revealed'||it.status==='skipped') done++;
    });
  });
  var pct = total>0 ? Math.round((done/total)*100) : 0;
  document.getElementById('cpFill').style.width=pct+'%';
  document.getElementById('cpLabel').textContent=pct+'% complete';
}
function isSlideCorrect(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice===slide.correct;
  return slide.flat.every(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).every(function(k){ return answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr); });
  });
}
function isSlideAttempted(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return slide.flat.some(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).some(function(k){ return ss.inputs[k] && String(ss.inputs[k]).trim()!==''; });
  });
}
function slideLabel(slide){
  var t = slide.kind==='case' ? slide.title : (slide.kind==='ar' ? slide.a : (slide.p||slide.text||''));
  t = String(t);
  return t.length>90 ? t.slice(0,90)+'…' : t;
}
function slideAnswerText(slide, item, correctSide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
    if(correctSide) return '('+LETTERS[slide.correct]+') '+opts[slide.correct];
    return item.choice!==undefined ? '('+LETTERS[item.choice]+') '+opts[item.choice] : '— not attempted —';
  }
  return slide.flat.map(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).map(function(k){
      return correctSide ? step.a[k] : (ss.inputs[k] || '—');
    }).join(', ');
  }).join('  |  ');
}

function renderFinished(){
  if(MODE==='quiz'){ renderQuizResults(); return; }
  var ts=state.tabs[activeTab];
  var correct=ts.items.filter(function(i){return i.status==='correct';}).length;
  var revealed=ts.items.filter(function(i){return i.status==='revealed';}).length;
  var skipped=ts.items.filter(function(i){return i.status==='skipped';}).length;
  var h='<div class="qcard done-card"><div class="big">✨</div><h2>Tab complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">You worked through all '+ts.items.length+' questions in this tab.</p>';
  if(!ts.recorded){ ts.recorded=true; addRecord('learning', activeTab, correct, revealed, skipped, ts.items.length); }
  h+='<div class="score-pills">'+
     '<span class="score-pill" style="background:var(--success-soft);color:var(--success);">'+correct+' correct</span>'+
     '<span class="score-pill" style="background:var(--danger-soft);color:var(--danger);">'+revealed+' revealed</span>'+
     '<span class="score-pill" style="background:var(--gold-soft);color:var(--retry-text);">'+skipped+' skipped</span></div>'+
     '<button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; ts.recorded=false; renderSlide(); });
  updateChapterProgress(); saveState();
}

function renderQuizResults(){
  var ts=state.tabs[activeTab];
  var slides=SLIDES[activeTab];
  var correctCount=0, attemptedCount=0;
  var rowsHtml = slides.map(function(slide,i){
    var item=ts.items[i];
    var ok=isSlideCorrect(activeTab,i);
    var att=isSlideAttempted(activeTab,i);
    if(ok) correctCount++;
    if(att) attemptedCount++;
    var tagCls = ok?'ok':(att?'bad':'na');
    var tagText = ok?'Correct':(att?'Incorrect':'Not attempted');
    var row='<div class="review-row">';
    row+='<span class="review-tag '+tagCls+'">Q'+(i+1)+' · '+tagText+'</span>';
    row+='<div class="review-q">'+fr(esc(slideLabel(slide)))+'</div>';
    row+='<div class="review-ans"><b>Your answer:</b> '+fr(esc(slideAnswerText(slide,item,false)))+'</div>';
    if(!ok) row+='<div class="review-ans" style="color:var(--success);"><b>Correct answer:</b> '+fr(esc(slideAnswerText(slide,item,true)))+'</div>';
    if(slide.sol) row+='<details class="rev-sol"><summary>Show solution</summary>'+solutionHTML(slide)+'</details>';
    row+='</div>';
    return row;
  }).join('');

  addRecord('quiz', activeTab, correctCount, 0, 0, slides.length);
  var h='<div class="qcard done-card" style="text-align:left;">';
  h+='<div style="text-align:center;"><div class="big">🏁</div><h2>Quiz complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">'+correctCount+' / '+slides.length+' correct · '+attemptedCount+' attempted</p></div>';
  h+='<div style="margin-top:16px;">'+rowsHtml+'</div>';
  h+='<div style="text-align:center;margin-top:6px;"><button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  h+='</div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; renderSlide(); });
  playSuccess();
  updateChapterProgress(); saveState();
}

/* ================= mode picker ================= */
function updateModePill(){
  var btn=document.getElementById('modePill');
  if(!btn) return;
  btn.textContent = MODE==='quiz' ? '📝 Quiz Mode · switch' : '📘 Learning Sheet · switch';
}
function showChrome(show){
  document.querySelector('.tabbar').style.display = show?'':'none';
  document.querySelector('.slide-progress').style.display = show?'':'none';
  document.querySelector('.navbar').style.display = show?'':'none';
  document.getElementById('paletteFab').style.display = show?'':'none';
}
function renderModePicker(){
  showChrome(false);
  var wrap=document.getElementById('wrap');
  wrap.innerHTML =
    '<div class="mode-pick">'+
      '<div class="mode-card" data-pick="learning"><div class="mode-icon">📘</div><h3>Learning Sheet</h3>'+
      '<p>Work through each question step by step with instant feedback — two tries, then the correct value is revealed right there so you can keep moving.</p></div>'+
      '<div class="mode-card" data-pick="quiz"><div class="mode-icon">📝</div><h3>Quiz Mode</h3>'+
      '<p>Attempt every question with no hints along the way. Your score and the full answer key are shown together once you finish the tab — just like the real exam.</p></div>'+
    '</div>';
  wrap.querySelectorAll('[data-pick]').forEach(function(card){
    card.addEventListener('click', function(){
      setMode(card.dataset.pick); activeTab='theory';
      document.getElementById('modePill').hidden=false;
      updateModePill();
      showChrome(true);
      buildTabbar();
      renderSlide();
    });
  });
}
document.getElementById('modePill').addEventListener('click', function(){
  if(!appState.mode){ return; }
  setMode(appState.mode==='quiz' ? 'learning' : 'quiz');
  updateModePill();
  showChrome(true);
  buildTabbar();
  renderSlide();
});

/* ================= boot ================= */
var _origRenderSlide = renderSlide;
renderSlide = function(){ _origRenderSlide(); updateChapterProgress(); updateModePill(); };


/* ================= theory tab ================= */
function renderTheory(){
  var wrap=document.getElementById('wrap');
  wrap.innerHTML='<div class="theory">'+fr(THEORY)+'</div>';
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Theory — notes, key ideas and worked examples';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
  wrap.querySelectorAll('[data-jump]').forEach(function(b){ b.addEventListener('click',function(){ var t=document.getElementById(b.dataset.jump); if(t) t.scrollIntoView({behavior:'smooth',block:'start'}); }); });
}
var _rsTheory = renderSlide;
renderSlide = function(){
  if(activeTab==='theory'){ renderTheory(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  document.querySelector('.slide-progress').style.display='';
  document.querySelector('.navbar').style.display='';
  document.getElementById('paletteFab').style.display='';
  _rsTheory();
};


/* ================= MYP criterion report ================= */
var CRIT_COL={A:'var(--accent-text)',B:'var(--gold)',C:'#8A6FC4',D:'#2F9AA0'};
function critStats(){
  return REPORT.map(function(r){
    var tabId=r[0], slides=SLIDES[tabId], ts=state&&state.tabs[tabId];
    var c=0,w=0,n=0;
    slides.forEach(function(sl,i){
      if(!ts||!ts.items[i]){ n++; return; }
      var it=ts.items[i];
      if(MODE==='learning'){
        if(it.status==='correct') c++; else if(it.status==='revealed') w++; else n++;
      } else {
        if(isSlideCorrect(tabId,i)) c++; else if(isSlideAttempted(tabId,i)) w++; else n++;
      }
    });
    var tot=slides.length, pct=tot?Math.round(c/tot*100):0;
    var lvl=Math.round(c/Math.max(tot,1)*8);
    return {tab:tabId,letter:r[1],name:r[2],c:c,w:w,n:n,tot:tot,pct:pct,lvl:lvl};
  });
}
function arcPath(cx,cy,r,a0,a1){
  if(a1-a0>=Math.PI*2-1e-6){ return 'M'+(cx-r)+','+cy+' a'+r+','+r+' 0 1,0 '+(2*r)+',0 a'+r+','+r+' 0 1,0 '+(-2*r)+',0 Z'; }
  var x0=cx+r*Math.sin(a0), y0=cy-r*Math.cos(a0), x1=cx+r*Math.sin(a1), y1=cy-r*Math.cos(a1);
  return 'M'+cx+','+cy+' L'+x0.toFixed(2)+','+y0.toFixed(2)+' A'+r+','+r+' 0 '+((a1-a0)>Math.PI?1:0)+',1 '+x1.toFixed(2)+','+y1.toFixed(2)+' Z';
}
function pieSVG(parts,size,hole,center,sub){
  var tot=parts.reduce(function(s,p){return s+p.v;},0), cx=size/2, cy=size/2, r=size/2-4, a=0, h='';
  if(!tot){ h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+r+'" style="fill:var(--paper-2);stroke:var(--rule)"/>'; }
  parts.forEach(function(p){ if(!p.v) return; var b=a+p.v/tot*Math.PI*2; h+='<path d="'+arcPath(cx,cy,r,a,b)+'" style="fill:'+p.col+';stroke:var(--card);stroke-width:2"><title>'+esc(p.label)+': '+p.v+'</title></path>'; a=b; });
  if(hole) h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+(r*hole)+'" style="fill:var(--card)"/>';
  if(center) h+='<text x="'+cx+'" y="'+(cy-(sub?4:0))+'" text-anchor="middle" dominant-baseline="middle" style="fill:var(--ink);font:700 '+(size>150?22:15)+'px Fraunces,serif">'+center+'</text>';
  if(sub) h+='<text x="'+cx+'" y="'+(cy+16)+'" text-anchor="middle" style="fill:var(--ink-soft);font:600 11px \'Source Sans 3\',sans-serif">'+sub+'</text>';
  return '<svg viewBox="0 0 '+size+' '+size+'" width="'+size+'" height="'+size+'" role="img">'+h+'</svg>';
}
function band(l){ return l===0?'0':(l<=2?'1–2':(l<=4?'3–4':(l<=6?'5–6':'7–8'))); }
function renderReport(){
  var st=critStats(), totC=0, totQ=0;
  st.forEach(function(s){ totC+=s.c; totQ+=s.tot; });
  var h='<div class="theory">';
  h+='<section class="note"><h2>Chapter test report</h2><p class="lt">'+(MODE==='quiz'?'<b>Quiz mode</b> results: answers are marked when you finish each test tab.':'<b>Learning mode</b> results: a question counts as correct only if you got it without the answer being revealed. Switch to Quiz mode for an exam-style score.')+'</p>';
  h+='<div class="rep-top"><div class="rep-pie">'+pieSVG(st.map(function(s){return {v:s.c,col:CRIT_COL[s.letter],label:'Criterion '+s.letter};}),200,0.55,totC+'/'+totQ,'correct')+'</div>';
  h+='<div class="rep-legend"><div class="rep-cap">Marks earned, by criterion</div>'+st.map(function(s){ return '<div class="rep-li"><span class="sw" style="background:'+CRIT_COL[s.letter]+'"></span><b>'+s.letter+'</b>&nbsp;'+esc(s.name)+'<span class="rep-n">'+s.c+' / '+s.tot+'</span></div>'; }).join('')+'</div></div></section>';
  h+='<div class="rep-grid">'+st.map(function(s){
    return '<div class="rep-card"><div class="rep-h"><span class="crit" style="background:'+CRIT_COL[s.letter]+'">'+s.letter+'</span>'+esc(s.name)+'</div>'+
      '<div class="rep-row">'+pieSVG([{v:s.c,col:'var(--success)',label:'Correct'},{v:s.w,col:'var(--danger)',label:'Incorrect'},{v:s.n,col:'var(--locked)',label:'Not attempted'}],120,0.5,s.pct+'%')+
      '<div class="rep-stats"><div><span class="sw" style="background:var(--success)"></span>Correct <b>'+s.c+'</b></div><div><span class="sw" style="background:var(--danger)"></span>Incorrect <b>'+s.w+'</b></div><div><span class="sw" style="background:var(--locked)"></span>Not attempted <b>'+s.n+'</b></div>'+
      '<div class="rep-lvl">Indicative level <b>'+s.lvl+'</b> / 8 <span>(band '+band(s.lvl)+')</span></div></div></div>'+
      '<button class="hub-btn" data-go="'+s.tab+'">Open Test '+s.letter+' →</button></div>';
  }).join('')+'</div>';
  h+='<p class="rep-note">Indicative level = fraction of questions correct × 8, rounded. It is a practice guide only; your teacher awards the real MYP criterion levels.</p></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Report — chapter test results by MYP criterion';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
}
var _rsReport = renderSlide;
renderSlide = function(){
  if(activeTab==='report'){ renderReport(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  _rsReport();
};


/* ================= skipped-question return ================= */
function firstSkippedIdx(ts){
  for(var i=0;i<ts.items.length;i++){
    var it=ts.items[i];
    if(MODE==='quiz'){ if(!isSlideAttempted(activeTab,i)) return i; }
    else if(it.status==='skipped'||it.status==='unanswered') return i;
  }
  return -1;
}
function skippedList(ts){
  var out=[]; for(var i=0;i<ts.items.length;i++){ var it=ts.items[i];
    if(MODE==='quiz' ? !isSlideAttempted(activeTab,i) : (it.status==='skipped'||it.status==='unanswered')) out.push(i); }
  return out;
}
function renderSkipGate(ts){
  var list=skippedList(ts);
  var h='<div class="qcard done-card"><div class="big">⏭️</div><h2>You skipped '+list.length+' question'+(list.length>1?'s':'')+'</h2>'+
    '<p style="color:var(--ink-soft);font-size:14px;">Answer them now, or submit the tab as it is. Answers are marked only when you submit.</p>'+
    '<div class="skip-chips">'+list.map(function(i){ return '<button class="chip skip-go" data-i="'+i+'">Q'+(i+1)+'</button>'; }).join('')+'</div>'+
    '<div class="skip-btns"><button class="btn btn-primary" id="btnGoSkipped">Answer skipped questions</button><button class="btn" id="btnSubmitAnyway">Submit anyway</button></div></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  var go=function(i){ ts.idx=i; ts.maxReached=Math.max(ts.maxReached,i); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); };
  document.getElementById('btnGoSkipped').addEventListener('click',function(){ go(list[0]); });
  document.querySelectorAll('.skip-go').forEach(function(b){ b.addEventListener('click',function(){ go(parseInt(b.dataset.i,10)); }); });
  document.getElementById('btnSubmitAnyway').addEventListener('click',function(){ ts.submitOK=true; renderFinished(); ts.submitOK=false; });
  saveState();
}
var _rfSkip = renderFinished;
renderFinished = function(){
  var ts=state.tabs[activeTab];
  if(MODE==='quiz' && !ts.submitOK && skippedList(ts).length){ renderSkipGate(ts); return; }
  _rfSkip();
  if(MODE==='learning'){
    var list=skippedList(ts);
    if(list.length){
      var card=document.querySelector('.done-card');
      if(card){ var d=document.createElement('div'); d.className='skip-btns';
        d.innerHTML='<button class="btn btn-primary" id="btnGoSkipped">Attempt skipped questions ('+list.length+')</button>';
        card.appendChild(d);
        document.getElementById('btnGoSkipped').addEventListener('click',function(){ ts.idx=list[0]; ts.recorded=false; renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); }
    }
  }
};

renderLogin();
})();
</script>
</body>
</html>
