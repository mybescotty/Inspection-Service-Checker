# First Bus Engineering — HTML Design Guide

Brand colours, component styles, and copy-paste CSS for internal tools built by **First Bus Franchise · Engineering**.

---

## Brand Palette

| Role | Name | Hex |
|------|------|-----|
| Primary brand | First Bus Navy | `#2D2A6E` |
| Accent / interactive | First Bus Pink | `#E5007D` |
| Accent hover | Deep Pink | `#C0006A` |
| Page background | Near-white | `#f5f5f7` |
| Panel / card | White | `#ffffff` |
| Border | Light lavender | `#e0e0ec` |
| Text primary | First Bus Navy | `#2D2A6E` |
| Text secondary | Muted purple-grey | `#6b6b8a` |
| Text on dark | White | `#ffffff` |

### Operational / Status Colours
These are kept consistent regardless of brand — they carry functional meaning and must not be changed to brand colours.

| State | Colour | Hex / value |
|-------|--------|-------------|
| Overdue — critical | Red tint row | `rgba(231,76,60,0.12)` |
| Overdue — warning | Amber tint row | `rgba(243,156,18,0.15)` |
| On time / today | Green tint row | `rgba(39,174,96,0.15)` |
| Date mismatch | Orange left border | `4px solid #e67e22` |
| VOR badge | Red | `#e74c3c` |
| Days overdue text | Red | `#c0392b` |
| Days today text | Green | `#27ae60` |

---

## CSS Variables — Copy into `:root`

```css
:root {
  --bg-page:       #f5f5f7;
  --bg-header:     #2D2A6E;
  --bg-panel:      #ffffff;
  --accent:        #E5007D;
  --accent-hover:  #C0006A;
  --row-red:       rgba(231,76,60,0.12);
  --row-amber:     rgba(243,156,18,0.15);
  --row-green:     rgba(39,174,96,0.15);
  --text-primary:  #2D2A6E;
  --text-secondary:#6b6b8a;
  --text-on-dark:  #ffffff;
  --border:        #e0e0ec;
}
```

---

## Component Patterns

### Header / Navigation Bar
```css
header {
  background: var(--bg-header);   /* #2D2A6E */
  color: var(--text-on-dark);
  padding: 0 20px;
  height: 56px;
  display: flex;
  align-items: center;
  gap: 20px;
}
```

Add the standard tagline under the `<h1>`:
```html
<header>
  <div>
    <h1>🔧 Your Tool Title</h1>
    <div style="font-size:10px;opacity:0.55;letter-spacing:0.05em;margin-top:2px">
      Designed by First Bus Franchise · Engineering
    </div>
  </div>
  <!-- ... rest of header ... -->
</header>
```

---

### Primary Button (Upload / Action)
```css
.upload-btn {
  background: var(--accent);    /* #E5007D */
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 7px 14px;
  font-size: 13px;
  cursor: pointer;
}
.upload-btn:hover { background: var(--accent-hover); }
```

---

### Toggle Button (Filter)
```css
.toggle-btn {
  background: none;
  border: 1px solid var(--accent);
  color: var(--accent);
  border-radius: 5px;
  padding: 4px 12px;
  font-size: 12px;
  cursor: pointer;
}
.toggle-btn:hover  { background: rgba(229,0,125,0.08); }
.toggle-btn.active { background: var(--accent); color: #fff; }
```

---

### Action Button (Email / Report)
```css
.action-btn {
  background: #27ae60;   /* green for positive actions */
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 4px 12px;
  font-size: 12px;
  cursor: pointer;
}
.action-btn:hover { background: #219a52; }
/* Override background inline for warning-style actions: style="background:#e67e22" */
```

---

### Data Table
```css
.wo-table { width: 100%; border-collapse: collapse; font-size: 13px; }
.wo-table th {
  background: var(--bg-header);   /* #2D2A6E */
  color: var(--text-on-dark);
  padding: 8px 10px;
  text-align: left;
  font-size: 12px;
}
.wo-table td { padding: 7px 10px; border-bottom: 1px solid #eaecef; }
.wo-table tbody tr:hover td { filter: brightness(0.96); }
```

---

### Sidebar Navigation Item
```css
.nav-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 7px 14px;
  cursor: pointer;
  font-size: 13px;
  border-radius: 0 20px 20px 0;
  margin-right: 8px;
  transition: background 0.15s;
}
.nav-item:hover  { background: rgba(229,0,125,0.08); }
.nav-item.active { background: var(--accent); color: #fff; }
```

---

### Badges / Tags
```css
/* OV / info badge — navy */
.badge-navy { background: #2D2A6E; color: #fff; border-radius: 3px; padding: 1px 5px; font-size: 11px; }

/* VOR / alert badge — red */
.badge-red  { background: #e74c3c; color: #fff; border-radius: 3px; padding: 1px 5px; font-size: 11px; }
```

---

## Checklist for New Tools

- [ ] `:root` variables block copied in
- [ ] `<header>` uses `var(--bg-header)` (`#2D2A6E`)
- [ ] Primary buttons use `var(--accent)` (`#E5007D`)
- [ ] Table `<th>` uses `var(--bg-header)` (`#2D2A6E`)
- [ ] Sidebar active items use `var(--accent)` (`#E5007D`)
- [ ] Hover states use `rgba(229,0,125,0.08)` (pink at 8% opacity)
- [ ] Page background is `#f5f5f7`, panels are `#ffffff`
- [ ] Tagline "Designed by First Bus Franchise · Engineering" in header
- [ ] Operational row colours (red/amber/green) left unchanged
