# 🚀 DÉMARRAGE RAPIDE - ORC 3D STUDIO PRO v6.1

## ⚡ Solution Ultra-Rapide (1 commande)

Vous avez des erreurs NumPy/PyTorch/TorchVision ? Utilisez le script d'installation automatique :

```bash
python install_dependencies.py
```

Ce script va :
1. ✅ Désinstaller les versions incompatibles
2. ✅ Installer NumPy 1.x (au lieu de 2.x)
3. ✅ Installer PyTorch 2.1.0 compatible
4. ✅ Installer toutes les dépendances
5. ✅ Vérifier que tout fonctionne

Ensuite :
```bash
python orc_3d_studio_v61_fixed.py
```

---

## 🔧 Solution Manuelle (si script automatique échoue)

### Étape 1: Nettoyer
```bash
pip uninstall numpy torch torchvision torchaudio timm -y
```

### Étape 2: Installer NumPy 1.x (CRITIQUE)
```bash
pip install "numpy<2.0"
```

### Étape 3: Installer PyTorch compatible
```bash
# Pour CPU ou Mac:
pip install torch==2.1.0 torchvision==0.16.0

# Pour GPU NVIDIA (CUDA 11.8):
pip install torch==2.1.0 torchvision==0.16.0 --index-url https://download.pytorch.org/whl/cu118
```

### Étape 4: Installer timm
```bash
pip install timm==0.9.12
```

### Étape 5: Installer le reste
```bash
pip install customtkinter pillow opencv-python scipy open3d
```

### Étape 6: Optionnels
```bash
pip install numba rembg
```

---

## 🎯 Vérification rapide

Testez que tout est OK :

```python
import numpy as np
import torch
import timm
import open3d

print("✅ NumPy:", np.__version__, "- Doit être 1.x!")
print("✅ PyTorch:", torch.__version__)
print("✅ Timm:", timm.__version__)
print("✅ Open3D:", open3d.__version__)
```

Si NumPy affiche 2.x → **PROBLÈME** :
```bash
pip install "numpy<2.0"
```

---

## 📋 Résumé des erreurs et solutions

| Erreur | Solution |
|--------|----------|
| `NumPy 1.x cannot run in NumPy 2.x` | `pip install "numpy<2.0"` |
| `cannot import name '_cast_Long'` | `pip install torch==2.1.0 torchvision==0.16.0` |
| `timm not found` | `pip install timm==0.9.12` |
| MiDaS ne charge pas | Vérifier internet OU décocher "IA Profondeur" |

---

## 🎮 Utilisation

1. **Lancer le programme** :
   ```bash
   python orc_3d_studio_v61_fixed.py
   ```

2. **Charger une image** : Cliquez "📂 Charger Image"

3. **Ajuster les paramètres** :
   - Résolution : 512px (bon compromis)
   - Relief : 15mm
   - Base : 3mm
   - Largeur : 100mm

4. **Options** :
   - ✅ **IA Profondeur** : Meilleure qualité (requiert MiDaS)
   - ⬜ **Supprimer fond** : Seulement si besoin

5. **Générer** : Cliquez "⚡ GÉNÉRER 3D"

6. **Exporter** : STL (impression 3D), OBJ (textures), ou PLY

---

## ⚠️ Si ça ne marche toujours pas

### Option A: Mode sans IA
Le programme fonctionne sans PyTorch/MiDaS :
1. Lancez le programme
2. Décochez "IA Profondeur (MiDaS)"
3. Générez quand même (utilise méthode classique)

### Option B: Environnement propre
```bash
# Créer un environnement virtuel propre
python -m venv venv_orc
venv_orc\Scripts\activate  # Windows
# OU
source venv_orc/bin/activate  # Linux/Mac

# Installer avec script auto
python install_dependencies.py

# Lancer
python orc_3d_studio_v61_fixed.py
```

---

## 🎯 Configuration testée (qui fonctionne)

```
Python: 3.10
numpy: 1.26.4 (PAS 2.x!)
torch: 2.1.0
torchvision: 0.16.0
timm: 0.9.12
open3d: 0.18.0
customtkinter: 5.2.1
opencv-python: 4.8.1
```

---

## 💡 Astuce

Si vous voulez juste **tester rapidement** :
1. Lancez le programme
2. Si erreur au démarrage → Décochez "IA Profondeur"
3. Ça marche quand même en mode classique !

---

**Version:** 6.1 FINAL
**Dernière mise à jour:** 31/01/2025