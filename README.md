# LPKIA Scholarship Rule Engine

Uji kelayakan beasiswa menggunakan aturan IF-THEN dari model Decision Tree (entropy, max_depth=4, min_samples_leaf=5).

## Isi folder

| File | Fungsi |
|------|--------|
| `index.html` | Rule engine interaktif (uji satu pendaftar, uji CSV, diagram pohon, daftar aturan). Buka langsung di browser. |
| `lpkia_decision_tree.ipynb` | Notebook Python untuk melatih Decision Tree, mengekstrak aturan, dan mengekspor `rules.json`. |

## Cara pakai

**Rule engine (HTML)**: buka `index.html` di browser, atau aktifkan GitHub Pages (Settings > Pages > Deploy from branch > `main` / root).

**Notebook**:

```bash
pip install pandas numpy scikit-learn matplotlib joblib jupyter
jupyter notebook lpkia_decision_tree.ipynb
```

Letakkan `data_beasiswa.csv` di folder yang sama dengan kolom `IPK, Penghasilan_Ortu, Jumlah_Tanggungan, Keaktifan_Organisasi, Layak` (1 = layak, 0 = tidak layak). Jika tidak ada, notebook memakai data sintetis.

Untuk memperbarui aturan di HTML, salin isi `rules.json` hasil notebook ke konstanta `const D=` di `index.html`.
