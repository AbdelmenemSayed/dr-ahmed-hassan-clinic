# Dr. Ahmed Hassan Dental Clinic — Personal Brand & UI/UX Project

A high-fidelity personal branding website for **Dr. Ahmed Hassan** (Specialist Dentist in Cosmetic Dentistry & Dental Implants).

## 🚀 Live Demo & Features

- **9 Responsive Pages**: Home, About Doctor, Services, Service Details (Dental Implants), Before & After Gallery, Certificates, Reviews, Booking, and Contact.
- **Interactive Before & After Slider**: Draggable comparison tool for smile transformations.
- **Certificate Popup Viewer**: Verified modal display for international board accreditations.
- **Interactive Mobile Prototype**: Simulated iPhone view with sticky action bar (`Call`, `WhatsApp`, `Book`).
- **Figma Design System**: Showcase of color swatches, Cairo & Inter typography scales, button states, and card components.
- **Behance / Dribbble Case Study Board**: Comprehensive 10-section project presentation.

---

## 🗄️ Supabase Database Integration (Optional)

To connect appointment booking submissions to a live **Supabase** database:

1. Create a project on [Supabase](https://supabase.com) under `abdelmenem9sayed123@gmail.com`.
2. Execute the following SQL query in the Supabase SQL Editor:

```sql
CREATE TABLE appointments (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  full_name TEXT NOT NULL,
  phone TEXT NOT NULL,
  service TEXT NOT NULL,
  preferred_date TIMESTAMP WITH TIME ZONE NOT NULL,
  notes TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Enable RLS & Row level security for insertion
ALTER TABLE appointments ENABLE ROW LEVEL SECURITY;
CREATE POLICY "Allow anonymous appointment booking" ON appointments FOR INSERT WITH CHECK (true);
```

3. Add your Supabase credentials inside `index.html`:
```html
<script>
  window.SUPABASE_URL = 'https://YOUR_PROJECT_REF.supabase.co';
  window.SUPABASE_ANON_KEY = 'YOUR_ANON_PUBLIC_KEY';
</script>
```

---

## 🛠️ Local Development & Deployment

To run locally:
```bash
npx serve .
```

To deploy to Vercel:
```bash
npx vercel --prod
```
