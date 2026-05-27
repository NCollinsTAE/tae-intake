# TAE Repair Intake Form

Internal web app for Tennessee Associated Electric to write up incoming repairs and send job tickets to sales@tn-associated.com.

## Live URL
https://ncollinstae.github.io/tae-intake/

## GitHub Repo
https://github.com/NCollinsTAE/tae-intake

---

## What It Does
- Intake form for new repair jobs (Create Job File phase)
- Smart fields — shows AC or DC electrical specs based on apparatus type
- Photo capture — opens iPad camera directly or pulls from photo library
- Sends email to sales@tn-associated.com via EmailJS with all form data + photos embedded
- Branded with TAE logo, red/blue color scheme

## Tech Stack
- Pure HTML/CSS/JS — single file, no framework
- EmailJS for email sending (no backend required)
- Hosted on GitHub Pages

## EmailJS Credentials
- Public Key:   TWC2GoUHtUlPEuS7T
- Service ID:   service_o97hs9v
- Template ID:  template_i1p0mvn
- To Email:     sales@tn-associated.com

## EmailJS Template (HTML body)
```html
<div style="font-family: Arial, sans-serif; max-width: 700px; margin: 0 auto;">
  <div style="background: #1B3A8C; padding: 16px 24px;">
    <span style="color: white; font-size: 22px; font-weight: 900;">TAE</span>
    <span style="color: #aab8d8; font-size: 13px; margin-left: 12px;">TENNESSEE ASSOCIATED ELECTRIC</span>
  </div>
  <div style="background: #E8302A; height: 3px;"></div>
  <div style="background: #f4f6f9; padding: 24px; border-bottom: 1px solid #d8dce6;">
    <h2 style="margin: 0; color: #1B3A8C; font-size: 22px;">New Repair Intake</h2>
    <p style="margin: 4px 0 0; color: #8a93b0; font-size: 13px;">{{customer}} &nbsp;·&nbsp; {{apparatus}} &nbsp;·&nbsp; {{date}}</p>
  </div>
  <div style="background: white; padding: 24px;">
    <pre style="font-family: Courier New, monospace; font-size: 13px; line-height: 1.7; color: #1a2340; white-space: pre-wrap; margin: 0;">{{body}}</pre>
  </div>
  <div style="padding: 20px 24px; border-top: 1px solid #d8dce6;">
    <p style="margin: 0 0 16px; font-size: 12px; font-weight: 700; color: #8a93b0;">PHOTOS</p>
    {{{photos_html}}}
  </div>
  <div style="background: #1B3A8C; padding: 14px 24px; text-align: center;">
    <p style="margin: 0; color: #aab8d8; font-size: 11px;">Tennessee Associated Electric &nbsp;|&nbsp; Knoxville, TN &nbsp;|&nbsp; Your Partner in Power.</p>
  </div>
</div>
```

## Known Issues / TODO
- Send button not confirmed working yet — debug alerts added to diagnose EmailJS loading issue
- Photos section: Take Photo (camera) and Choose from Library both implemented, thumbnails show on screen
- Banner removal: setup banner removed from UI but may still appear due to GitHub Pages cache — clear browser cache to resolve
- Next phase to build: Inspection Phase ticket form

## Form Sections
1. Job Information — Date, taken by, quantity, customer name, PO#, contact
2. Apparatus Information — Type (24 options grouped), manufacture, serial, model, stock, spec, type, ID, date code, frame + conditional AC or DC electrical specs
3. Repair Details — Rush order, return date, problem description, visual condition, notes
4. Photos — Camera + library upload with thumbnail preview

## Apparatus Types
AC Motors: AC ASynchronous, AC Synchronous, AC Wound Rotor, AC ASynchronous Motor & Blower, AC ASynchronous Vertical
DC Motors: DC, DC Armature, DC Compound, DC Permanent Magnet, DC Series, DC Shunt, DC Stabilized
Servo/Stepper: Servo, Stepper
Drives: AC Drive, DC Drive, Servo Drive, Stepper Drive
Generators: Standby Generator, Permanent Magnet Synchronous
Other: Pump, Pump & Motor, Tachometer, Stator Only, Shaft, SEW-EURODRIVE Motor & Gearbox, Gearbox

## Brand Colors
- Red:  #E8302A
- Blue: #1B3A8C
- BG:   #f4f6f9
- Text: #1a2340

## EASA Reference
- Area: 1.0.0 Receiving
- Section: 1.1.0 Apparatus
- Procedure: Document and Tag
- Doc No. 1.1.1 Rev 002
