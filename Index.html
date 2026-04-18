import { useState, useEffect } from "react";

const G  = "#3B6D11";
const GL = "#EAF3DE";
const GM = "#C0DD97";
const A  = "#854F0B";
const AL = "#FAEEDA";
const AM = "#FAC775";

const MEALS = [
  { id: "pre_breakfast", time: "5–7 AM",   label: "Pre-breakfast", color: "#185FA5",
    note: "Aids lipid reduction",
    opts: ["Warm water + 1 tsp fenugreek seeds", "Warm lemon water", "Warm water + chia seeds", "Warm water + amla juice"] },
  { id: "breakfast",     time: "8–9 AM",   label: "Breakfast",     color: "#3B6D11",
    note: "Steam only · No oil · Lowers LDL by 5–10%",
    opts: ["Oats / Barley porridge", "Rava idli + Sambar (2 nos)", "Oats upma", "Whole wheat dosa + Sambar"] },
  { id: "mid_morning",   time: "10–11 AM", label: "Mid-morning",   color: "#0F6E56",
    note: "Healthy fat · Boosts HDL",
    opts: ["Buttermilk (low fat) + handful almonds", "Handful almonds / walnuts", "Coconut water + nuts", "Low fat buttermilk"] },
  { id: "lunch",         time: "1–2 PM",   label: "Lunch",         color: "#534AB7",
    note: "Fiber-rich · Avoid white rice",
    opts: ["Brown rice (1 cup) + Dal + Veg Poriyal", "Chapati + Dal + Vegetables", "Millet rice + Sambar", "Brown rice + Fish curry (small)"] },
  { id: "snack",         time: "4–5 PM",   label: "Snack",         color: "#BA7517",
    note: "Soluble fiber · Blocks cholesterol absorption",
    opts: ["Apple / Guava + Green tea", "Avocado + Green tea", "Mixed fruits + Green tea", "Roasted nuts + Green tea"] },
  { id: "dinner",        time: "8–9 PM",   label: "Dinner",        color: "#993556",
    note: "Easy to digest · Light meal",
    opts: ["Ragi dosa (2) + Veg Kootu", "Ragi dosa (2) + Soya curry", "Ragi dosa (2) + Fish (grilled)", "Wheat dosa + Veg Kootu"] },
  { id: "bedtime",       time: "Bedtime",  label: "Bedtime",       color: "#534AB7",
    note: "Anti-inflammatory",
    opts: ["Warm turmeric milk", "Warm turmeric + pepper milk", "Warm ginger + turmeric milk", "Warm ashwagandha milk"] },
];

const MONTH_NAMES = ["January","February","March","April","May","June","July","August","September","October","November","December"];
const DAYS_ABBR   = ["Su","Mo","Tu","We","Th","Fr","Sa"];

const daysIn   = (y, m) => new Date(y, m + 1, 0).getDate();
const firstDay = (y, m) => new Date(y, m, 1).getDay();
const mkMId    = (y, m) => `${y}-${String(m + 1).padStart(2, "0")}`;
const mkDKey   = (y, m, d) => `${y}-${String(m + 1).padStart(2, "0")}-${String(d).padStart(2, "0")}`;

async function sg(k)   { try { const r = await window.storage.get(k); return r ? JSON.parse(r.value) : null; } catch { return null; } }
async function ss(k,v) { try { await window.storage.set(k, JSON.stringify(v)); } catch {} }

function fmtTime(iso) {
  try { return new Date(iso).toLocaleTimeString("en-IN", { hour: "2-digit", minute: "2-digit" }); }
  catch { return ""; }
}

function Dot({ color, size = 8 }) {
  return <span style={{ display:"inline-block", width:size, height:size, borderRadius:"50%", background:color, flexShrink:0 }} />;
}

// ── Meal row ──────────────────────────────────────────────────────────────────
function MealRow({ meal, data, opts, onSave, onCheck, onAddOpt }) {
  const savedSel = data?.selected || opts[0];
  const [pending,   setPending]   = useState(savedSel);
  const [saveState, setSaveState] = useState("idle");
  const [adding,    setAdding]    = useState(false);
  const [newOpt,    setNewOpt]    = useState("");

  const checked = data?.checked || false;

  useEffect(() => {
    setPending(data?.selected || opts[0]);
    setSaveState("idle");
  }, [data?.selected]);

  function handleDropdown(e) {
    const v = e.target.value;
    if (v === "__add__") { setAdding(true); return; }
    setPending(v);
    setSaveState(v !== (data?.selected || opts[0]) ? "dirty" : "idle");
  }

  async function handleSave() {
    setSaveState("saving");
    await onSave(pending);
    setSaveState("saved");
    setTimeout(() => setSaveState("idle"), 2200);
  }

  function commitCustom() {
    if (!newOpt.trim()) return;
    onAddOpt(newOpt.trim());
    setPending(newOpt.trim());
    setSaveState("dirty");
    setNewOpt(""); setAdding(false);
  }

  const isDirty = saveState === "dirty";
  const isSaved = saveState === "saved";

  return (
    <div style={{
      borderRadius:"var(--border-radius-lg)",
      border:`0.5px solid ${checked ? GM : "var(--color-border-tertiary)"}`,
      background: checked ? GL : "var(--color-background-primary)",
      marginBottom:10, overflow:"hidden",
      transition:"background 0.25s, border-color 0.25s",
    }}>
      {/* Header */}
      <div style={{
        display:"flex", alignItems:"center", justifyContent:"space-between",
        padding:"10px 14px",
        background:"var(--color-background-secondary)",
        borderBottom:`0.5px solid ${checked ? GM : "var(--color-border-tertiary)"}`,
      }}>
        <div style={{ display:"flex", alignItems:"center", gap:10 }}>
          <Dot color={meal.color} size={9} />
          <span style={{ fontSize:13, fontWeight:500, color:"var(--color-text-primary)" }}>{meal.label}</span>
          <span style={{
            fontSize:11, color:"var(--color-text-secondary)",
            background:"var(--color-background-primary)",
            border:"0.5px solid var(--color-border-tertiary)",
            borderRadius:100, padding:"2px 8px",
          }}>{meal.time}</span>
        </div>

        {/* Mark done */}
        <button onClick={() => onCheck(!checked)} style={{
          display:"flex", alignItems:"center", gap:5,
          padding:"5px 12px", borderRadius:100, cursor:"pointer", fontSize:12, fontWeight:500,
          background: checked ? G : "var(--color-background-primary)",
          color: checked ? "#fff" : "var(--color-text-secondary)",
          border:`0.5px solid ${checked ? G : "var(--color-border-secondary)"}`,
          transition:"all 0.15s",
        }}>
          <span style={{
            display:"inline-flex", alignItems:"center", justifyContent:"center",
            width:14, height:14, borderRadius:"50%",
            border: checked ? "none" : "1.5px solid var(--color-border-secondary)",
            background: checked ? "rgba(255,255,255,0.3)" : "transparent",
            fontSize:9, color:"#fff",
          }}>{checked ? "✓" : ""}</span>
          {checked ? "Done" : "Mark done"}
        </button>
      </div>

      {/* Body */}
      <div style={{ padding:"12px 14px" }}>
        <p style={{ margin:"0 0 10px", fontSize:11, color:"var(--color-text-secondary)", lineHeight:1.4 }}>
          {meal.note}
        </p>
        <div style={{ fontSize:11, fontWeight:500, color:"var(--color-text-secondary)", marginBottom:6, textTransform:"uppercase", letterSpacing:"0.04em" }}>
          Meal selection
        </div>
        <div style={{ display:"flex", gap:8, alignItems:"flex-start" }}>
          <select value={pending} onChange={handleDropdown} style={{
            flex:1, fontSize:13, padding:"8px 10px",
            background:"var(--color-background-secondary)",
            border:`0.5px solid ${isDirty ? AM : "var(--color-border-secondary)"}`,
            borderRadius:"var(--border-radius-md)", outline:"none",
            color:"var(--color-text-primary)", cursor:"pointer",
            transition:"border-color 0.15s",
          }}>
            {opts.map(o => <option key={o} value={o}>{o}</option>)}
            <option value="__add__">+ Add custom option...</option>
          </select>

          <button onClick={handleSave} style={{
            padding:"8px 16px", fontSize:12, fontWeight:500,
            borderRadius:"var(--border-radius-md)", border:"none",
            whiteSpace:"nowrap", cursor: isDirty ? "pointer" : "default",
            transition:"all 0.2s",
            background: isSaved ? G : isDirty ? A : "var(--color-background-secondary)",
            color: (isSaved || isDirty) ? "#fff" : "var(--color-text-secondary)",
          }}>
            {isSaved ? "✓ Saved" : isDirty ? "Save" : "Saved"}
          </button>
        </div>

        {adding && (
          <div style={{ display:"flex", gap:6, marginTop:8 }}>
            <input autoFocus value={newOpt} onChange={e => setNewOpt(e.target.value)}
              onKeyDown={e => { if (e.key === "Enter") commitCustom(); if (e.key === "Escape") { setAdding(false); setNewOpt(""); } }}
              placeholder="Type your custom meal..."
              style={{
                flex:1, fontSize:13, padding:"7px 10px",
                border:`0.5px solid ${G}`, borderRadius:"var(--border-radius-md)",
                outline:"none", background:"var(--color-background-primary)", color:"var(--color-text-primary)",
              }} />
            <button onClick={commitCustom} style={{
              padding:"7px 12px", background:G, color:"#fff",
              border:"none", borderRadius:"var(--border-radius-md)", fontSize:12, fontWeight:500, cursor:"pointer",
            }}>Add</button>
            <button onClick={() => { setAdding(false); setNewOpt(""); }} style={{
              padding:"7px 8px", background:"var(--color-background-secondary)",
              border:"0.5px solid var(--color-border-tertiary)",
              borderRadius:"var(--border-radius-md)", fontSize:12, cursor:"pointer", color:"var(--color-text-secondary)",
            }}>✕</button>
          </div>
        )}

        {isDirty && (
          <p style={{ margin:"7px 0 0", fontSize:11, color:A }}>
            Unsaved changes — tap Save to confirm.
          </p>
        )}
      </div>
    </div>
  );
}

// ── Calendar view ─────────────────────────────────────────────────────────────
function CalendarView({ year, month, dayData, onSelect, todayKey }) {
  const days  = daysIn(year, month);
  const start = firstDay(year, month);
  const cells = Array(start).fill(null).concat(Array.from({ length:days }, (_,i) => i+1));

  function info(d) {
    const dd      = dayData[mkDKey(year, month, d)];
    const checked = dd ? MEALS.filter(m => dd[m.id]?.checked).length : 0;
    return { pct: checked / MEALS.length, loggedIn: !!dd?._loggedIn };
  }

  return (
    <div>
      <div style={{ display:"flex", gap:14, marginBottom:14, flexWrap:"wrap" }}>
        {[["All done",G],["Partial",A],["Logged in","#185FA5"],["Not started","var(--color-border-secondary)"]].map(([label,color]) => (
          <div key={label} style={{ display:"flex", alignItems:"center", gap:6, fontSize:12, color:"var(--color-text-secondary)" }}>
            <Dot color={color} size={8} />{label}
          </div>
        ))}
      </div>
      <div style={{ display:"grid", gridTemplateColumns:"repeat(7,1fr)", gap:4, marginBottom:4 }}>
        {DAYS_ABBR.map(d => (
          <div key={d} style={{ textAlign:"center", fontSize:11, fontWeight:500, color:"var(--color-text-secondary)", padding:"3px 0" }}>{d}</div>
        ))}
      </div>
      <div style={{ display:"grid", gridTemplateColumns:"repeat(7,1fr)", gap:4 }}>
        {cells.map((d,i) => {
          if (!d) return <div key={`_${i}`} />;
          const k   = mkDKey(year, month, d);
          const { pct, loggedIn } = info(d);
          const isT = k === todayKey;
          return (
            <button key={k} onClick={() => onSelect(k)} style={{
              display:"flex", flexDirection:"column", alignItems:"center", justifyContent:"center",
              gap:4, padding:"9px 2px",
              background: pct >= 1 ? GL : pct > 0 ? AL : "var(--color-background-primary)",
              border: isT ? `2px solid ${A}` : "0.5px solid var(--color-border-tertiary)",
              borderRadius:"var(--border-radius-md)", cursor:"pointer", transition:"background 0.15s",
            }}>
              <span style={{ fontSize:13, fontWeight:isT?500:400, color:isT?A:"var(--color-text-primary)" }}>{d}</span>
              {pct > 0 && (
                <div style={{ width:"68%", height:3, borderRadius:2, background:"var(--color-border-tertiary)", overflow:"hidden" }}>
                  <div style={{ width:`${Math.round(pct*100)}%`, height:"100%", background:pct>=1?G:A, borderRadius:2 }} />
                </div>
              )}
              {loggedIn && pct === 0 && <Dot color="#185FA5" size={5} />}
            </button>
          );
        })}
      </div>
    </div>
  );
}

// ── Check-in banner ───────────────────────────────────────────────────────────
function CheckInBanner({ loggedIn, loginTime, onCheckIn }) {
  return loggedIn ? (
    <div style={{
      display:"flex", alignItems:"center", justifyContent:"space-between",
      padding:"12px 16px",
      background:GL, border:`0.5px solid ${GM}`,
      borderRadius:"var(--border-radius-lg)", marginBottom:14,
    }}>
      <div style={{ display:"flex", alignItems:"center", gap:12 }}>
        <div style={{
          width:32, height:32, borderRadius:"50%", background:G,
          display:"flex", alignItems:"center", justifyContent:"center",
          fontSize:14, color:"#fff", fontWeight:500, flexShrink:0,
        }}>✓</div>
        <div>
          <div style={{ fontSize:13, fontWeight:500, color:G }}>Day logged in</div>
          <div style={{ fontSize:11, color:"var(--color-text-secondary)", marginTop:1 }}>Checked in at {loginTime}</div>
        </div>
      </div>
      <span style={{
        fontSize:11, color:G, fontWeight:500,
        background:GM, borderRadius:100, padding:"4px 10px",
      }}>Active</span>
    </div>
  ) : (
    <div style={{
      display:"flex", alignItems:"center", justifyContent:"space-between",
      padding:"14px 16px",
      background:"var(--color-background-secondary)",
      border:"0.5px solid var(--color-border-tertiary)",
      borderRadius:"var(--border-radius-lg)", marginBottom:14,
    }}>
      <div>
        <div style={{ fontSize:13, fontWeight:500, color:"var(--color-text-primary)" }}>Start tracking this day</div>
        <div style={{ fontSize:11, color:"var(--color-text-secondary)", marginTop:2 }}>
          Tap Log In to begin your meal log
        </div>
      </div>
      <button onClick={onCheckIn} style={{
        padding:"9px 20px", background:G, color:"#fff",
        border:"none", borderRadius:"var(--border-radius-md)",
        fontSize:13, fontWeight:500, cursor:"pointer", whiteSpace:"nowrap",
      }}>Log In</button>
    </div>
  );
}

// ── Progress bar ──────────────────────────────────────────────────────────────
function ProgressBar({ checked, total }) {
  const pct = total > 0 ? Math.round((checked / total) * 100) : 0;
  return (
    <div style={{ marginBottom:16 }}>
      <div style={{ display:"flex", justifyContent:"space-between", alignItems:"baseline", marginBottom:6 }}>
        <span style={{ fontSize:12, color:"var(--color-text-secondary)" }}>Daily progress</span>
        <span style={{ fontSize:13, fontWeight:500, color:pct===100?G:"var(--color-text-primary)" }}>
          {checked} / {total} meals done
        </span>
      </div>
      <div style={{ height:6, borderRadius:3, background:"var(--color-border-tertiary)", overflow:"hidden" }}>
        <div style={{ height:"100%", borderRadius:3, width:`${pct}%`, background:pct===100?G:A, transition:"width 0.3s ease" }} />
      </div>
      {pct === 100 && (
        <p style={{ margin:"6px 0 0", fontSize:12, color:G, fontWeight:500 }}>All meals completed!</p>
      )}
    </div>
  );
}

// ── Add month modal ───────────────────────────────────────────────────────────
function AddMonthModal({ newY, newM, setNewY, setNewM, onAdd, onClose }) {
  return (
    <div style={{
      background:"rgba(0,0,0,0.45)", display:"flex", alignItems:"center",
      justifyContent:"center", padding:20, minHeight:320,
      borderRadius:"var(--border-radius-lg)",
    }}>
      <div style={{
        background:"var(--color-background-primary)",
        borderRadius:"var(--border-radius-xl)",
        border:"0.5px solid var(--color-border-tertiary)",
        padding:"24px 20px", width:"100%", maxWidth:320,
      }}>
        <h3 style={{ fontSize:16, fontWeight:500, margin:"0 0 4px", color:"var(--color-text-primary)" }}>Add month</h3>
        <p style={{ margin:"0 0 18px", fontSize:12, color:"var(--color-text-secondary)" }}>Track meals for any month</p>
        <div style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:12, marginBottom:20 }}>
          <div>
            <div style={{ fontSize:11, fontWeight:500, color:"var(--color-text-secondary)", marginBottom:6 }}>Month</div>
            <select value={newM} onChange={e => setNewM(Number(e.target.value))} style={{
              width:"100%", padding:"9px", fontSize:13,
              background:"var(--color-background-secondary)",
              border:"0.5px solid var(--color-border-secondary)",
              borderRadius:"var(--border-radius-md)", outline:"none", color:"var(--color-text-primary)",
            }}>
              {MONTH_NAMES.map((n,i) => <option key={i} value={i}>{n}</option>)}
            </select>
          </div>
          <div>
            <div style={{ fontSize:11, fontWeight:500, color:"var(--color-text-secondary)", marginBottom:6 }}>Year</div>
            <input type="number" value={newY} onChange={e => setNewY(Number(e.target.value))} style={{
              width:"100%", padding:"9px", fontSize:13, boxSizing:"border-box",
              background:"var(--color-background-secondary)",
              border:"0.5px solid var(--color-border-secondary)",
              borderRadius:"var(--border-radius-md)", outline:"none", color:"var(--color-text-primary)",
            }} />
          </div>
        </div>
        <div style={{ display:"flex", gap:8 }}>
          <button onClick={onClose} style={{
            flex:1, padding:"10px", fontSize:13, fontWeight:500, cursor:"pointer",
            background:"var(--color-background-secondary)",
            border:"0.5px solid var(--color-border-secondary)",
            borderRadius:"var(--border-radius-md)", color:"var(--color-text-secondary)",
          }}>Cancel</button>
          <button onClick={onAdd} style={{
            flex:2, padding:"10px", fontSize:13, fontWeight:500, cursor:"pointer",
            background:G, color:"#fff", border:"none", borderRadius:"var(--border-radius-md)",
          }}>Add {MONTH_NAMES[newM]} {newY}</button>
        </div>
      </div>
    </div>
  );
}

// ── Main app ──────────────────────────────────────────────────────────────────
export default function App() {
  const now      = new Date();
  const todayKey = mkDKey(now.getFullYear(), now.getMonth(), now.getDate());

  const [months,   setMonths]   = useState([]);
  const [activeId, setActiveId] = useState(null);
  const [dayKey,   setDayKey]   = useState(null);
  const [dayData,  setDayData]  = useState({});
  const [mealOpts, setMealOpts] = useState(() => Object.fromEntries(MEALS.map(m => [m.id, [...m.opts]])));
  const [loading,  setLoading]  = useState(true);
  const [showAdd,  setShowAdd]  = useState(false);
  const [newY,     setNewY]     = useState(now.getFullYear());
  const [newM,     setNewM]     = useState(now.getMonth());

  const activeMonth = months.find(m => m.id === activeId);

  useEffect(() => {
    (async () => {
      const [savedMonths, savedOpts] = await Promise.all([sg("chol-months"), sg("chol-opts")]);
      if (savedOpts) setMealOpts(savedOpts);
      if (savedMonths && savedMonths.length > 0) {
        setMonths(savedMonths);
        setActiveId(savedMonths[savedMonths.length - 1].id);
      } else {
        const def = { id:mkMId(now.getFullYear(),now.getMonth()), year:now.getFullYear(), month:now.getMonth(), label:`${MONTH_NAMES[now.getMonth()]} ${now.getFullYear()}` };
        setMonths([def]); setActiveId(def.id);
        await ss("chol-months", [def]);
      }
      setLoading(false);
    })();
  }, []);

  useEffect(() => {
    if (!activeMonth) return;
    (async () => {
      const { year, month } = activeMonth;
      const data = {};
      for (let d = 1; d <= daysIn(year, month); d++) {
        const k = mkDKey(year, month, d);
        const v = await sg(`cd-${k}`);
        if (v) data[k] = v;
      }
      setDayData(data);
    })();
  }, [activeId]);

  async function patchDay(dk, updates) {
    const merged = { ...(dayData[dk] || {}), ...updates };
    setDayData(prev => ({ ...prev, [dk]: merged }));
    await ss(`cd-${dk}`, merged);
  }

  async function saveMealSel(dk, mealId, selected) {
    const existing = dayData[dk] || {};
    const meal     = MEALS.find(x => x.id === mealId);
    const def      = { selected:(mealOpts[mealId]||meal.opts)[0], checked:false };
    const updated  = { ...existing, [mealId]:{ ...def, ...existing[mealId], selected } };
    setDayData(prev => ({ ...prev, [dk]:updated }));
    await ss(`cd-${dk}`, updated);
  }

  async function checkMeal(dk, mealId, checked) {
    const existing = dayData[dk] || {};
    const meal     = MEALS.find(x => x.id === mealId);
    const def      = { selected:(mealOpts[mealId]||meal.opts)[0], checked:false };
    const updated  = { ...existing, [mealId]:{ ...def, ...existing[mealId], checked } };
    setDayData(prev => ({ ...prev, [dk]:updated }));
    await ss(`cd-${dk}`, updated);
  }

  async function addOpt(mealId, opt) {
    const updated = { ...mealOpts, [mealId]:[...(mealOpts[mealId]||[]), opt] };
    setMealOpts(updated);
    await ss("chol-opts", updated);
  }

  async function addMonth() {
    const id = mkMId(newY, newM);
    if (months.find(m => m.id === id)) { setActiveId(id); setShowAdd(false); return; }
    const m       = { id, year:newY, month:newM, label:`${MONTH_NAMES[newM]} ${newY}` };
    const updated = [...months, m].sort((a,b) => a.id.localeCompare(b.id));
    setMonths(updated); setActiveId(id); setShowAdd(false);
    await ss("chol-months", updated);
  }

  function getMD(dk, mealId) {
    const meal = MEALS.find(x => x.id === mealId);
    return dayData[dk]?.[mealId] || { selected:(mealOpts[mealId]||meal.opts)[0], checked:false };
  }

  const checkedCount = dayKey ? MEALS.filter(m => dayData[dayKey]?.[m.id]?.checked).length : 0;
  const dayMeta      = dayKey ? (dayData[dayKey] || {}) : {};
  const loggedIn     = !!dayMeta._loggedIn;
  const loginTime    = loggedIn ? fmtTime(dayMeta._loginTime) : "";

  let dayLabel = "";
  if (dayKey) {
    const [y,mo,d] = dayKey.split("-").map(Number);
    dayLabel = new Date(y,mo-1,d).toLocaleDateString("en-IN",{ weekday:"long", day:"numeric", month:"long", year:"numeric" });
  }

  if (loading) return (
    <div style={{ display:"flex", alignItems:"center", justifyContent:"center", minHeight:200, color:"var(--color-text-secondary)", fontSize:14 }}>
      Loading...
    </div>
  );

  return (
    <div style={{ fontFamily:"var(--font-sans)", color:"var(--color-text-primary)", position:"relative", minHeight:showAdd?520:undefined }}>
      <h2 className="sr-only">Cholesterol control daily meal tracker</h2>

      {/* ── Header ── */}
      <div style={{ padding:"16px 0 14px", borderBottom:"0.5px solid var(--color-border-tertiary)", marginBottom:16 }}>
        <div style={{ display:"flex", alignItems:"center", gap:10 }}>
          <div style={{
            width:34, height:34, borderRadius:"var(--border-radius-md)", background:G,
            display:"flex", alignItems:"center", justifyContent:"center", flexShrink:0,
          }}>
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none">
              <circle cx="9" cy="9" r="7" stroke="white" strokeWidth="1.5"/>
              <path d="M6 9l2 2 4-4" stroke="white" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round"/>
            </svg>
          </div>
          <div>
            <h1 style={{ fontSize:18, fontWeight:500, margin:0, color:"var(--color-text-primary)" }}>Meal tracker</h1>
            <div style={{ fontSize:11, color:"var(--color-text-secondary)", marginTop:1 }}>Cholesterol control diet plan</div>
          </div>
        </div>
      </div>

      {/* ── Month tabs ── */}
      <div style={{ marginBottom:16 }}>
        <div style={{ fontSize:11, fontWeight:500, color:"var(--color-text-secondary)", marginBottom:8, textTransform:"uppercase", letterSpacing:"0.04em" }}>Month</div>
        <div style={{ display:"flex", gap:6, flexWrap:"wrap" }}>
          {months.map(m => (
            <button key={m.id} onClick={() => { setActiveId(m.id); setDayKey(null); }} style={{
              padding:"6px 14px", borderRadius:100, fontSize:13, fontWeight:500, cursor:"pointer",
              border:"none", whiteSpace:"nowrap", transition:"all 0.15s",
              background: activeId===m.id ? G : "var(--color-background-secondary)",
              color: activeId===m.id ? "#fff" : "var(--color-text-secondary)",
              outline: activeId===m.id ? "none" : "0.5px solid var(--color-border-secondary)",
            }}>{m.label}</button>
          ))}
          <button onClick={() => setShowAdd(true)} style={{
            padding:"6px 14px", borderRadius:100, fontSize:13, fontWeight:500, cursor:"pointer",
            background:"var(--color-background-secondary)", color:"var(--color-text-secondary)",
            border:"0.5px solid var(--color-border-secondary)", whiteSpace:"nowrap",
          }}>+ Add month</button>
        </div>
      </div>

      {/* ── Day detail ── */}
      {dayKey && (
        <div>
          <button onClick={() => setDayKey(null)} style={{
            background:"none", border:"none", color:G, fontWeight:500, fontSize:13,
            cursor:"pointer", padding:0, marginBottom:14, display:"flex", alignItems:"center", gap:4,
          }}>
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none">
              <path d="M9 2L4 7l5 5" stroke={G} strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round"/>
            </svg>
            Back to {activeMonth?.label}
          </button>

          <h2 style={{ fontSize:18, fontWeight:500, margin:"0 0 14px", color:"var(--color-text-primary)" }}>
            {dayLabel}
          </h2>

          <CheckInBanner loggedIn={loggedIn} loginTime={loginTime}
            onCheckIn={() => patchDay(dayKey, { _loggedIn:true, _loginTime:new Date().toISOString() })} />

          <ProgressBar checked={checkedCount} total={MEALS.length} />

          <div style={{ display:"flex", alignItems:"baseline", justifyContent:"space-between", marginBottom:10 }}>
            <div style={{ fontSize:11, fontWeight:500, color:"var(--color-text-secondary)", textTransform:"uppercase", letterSpacing:"0.04em" }}>
              Meal log — {MEALS.length} sections
            </div>
            <div style={{ fontSize:11, color:"var(--color-text-secondary)" }}>
              Select · Save · Mark done
            </div>
          </div>

          {MEALS.map(meal => {
            const data = getMD(dayKey, meal.id);
            return (
              <MealRow key={meal.id} meal={meal} data={data}
                opts={mealOpts[meal.id] || meal.opts}
                onSave={sel => saveMealSel(dayKey, meal.id, sel)}
                onCheck={chk => checkMeal(dayKey, meal.id, chk)}
                onAddOpt={opt => addOpt(meal.id, opt)} />
            );
          })}

          <div style={{
            marginTop:18, padding:"14px 16px",
            background:AL, border:`0.5px solid ${AM}`,
            borderRadius:"var(--border-radius-lg)",
          }}>
            <div style={{ display:"flex", alignItems:"center", gap:8, marginBottom:6 }}>
              <Dot color={A} size={6} />
              <span style={{ fontSize:11, fontWeight:500, color:A, textTransform:"uppercase", letterSpacing:"0.04em" }}>Avoid today</span>
            </div>
            <p style={{ margin:0, fontSize:13, color:"#633806", lineHeight:1.6 }}>
              Packaged cakes, biscuits, fast foods, fried foods, butter, cheese, cream, red meat. Limit salt.
            </p>
          </div>
        </div>
      )}

      {/* ── Calendar view ── */}
      {!dayKey && activeMonth && (
        <div>
          <div style={{ display:"flex", alignItems:"baseline", justifyContent:"space-between", marginBottom:14 }}>
            <h2 style={{ fontSize:16, fontWeight:500, margin:0 }}>{activeMonth.label}</h2>
            <span style={{ fontSize:12, color:"var(--color-text-secondary)" }}>Tap a day to log meals</span>
          </div>
          <CalendarView year={activeMonth.year} month={activeMonth.month}
            dayData={dayData} onSelect={setDayKey} todayKey={todayKey} />

          <div style={{
            marginTop:20, padding:"12px 16px",
            background:"var(--color-background-secondary)",
            border:"0.5px solid var(--color-border-tertiary)",
            borderRadius:"var(--border-radius-lg)",
          }}>
            <p style={{ margin:0, fontSize:12, color:"var(--color-text-secondary)", lineHeight:1.7 }}>
              <strong style={{ color:"var(--color-text-primary)", fontWeight:500 }}>How to use:</strong>{" "}
              Tap a day on the calendar → press <strong style={{ fontWeight:500 }}>Log In</strong> to check in for the day → pick your meal from the dropdown → press <strong style={{ fontWeight:500 }}>Save</strong> to record it → tap <strong style={{ fontWeight:500 }}>Mark done</strong> after eating.
            </p>
          </div>
        </div>
      )}

      {/* ── Add month overlay ── */}
      {showAdd && (
        <div style={{ position:"absolute", inset:0, zIndex:10, borderRadius:"var(--border-radius-lg)" }}>
          <AddMonthModal newY={newY} newM={newM} setNewY={setNewY} setNewM={setNewM}
            onAdd={addMonth} onClose={() => setShowAdd(false)} />
        </div>
      )}
    </div>
  );
}
