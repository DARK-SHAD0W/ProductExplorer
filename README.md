# Product Explorer

Application Android Jetpack Compose développée dans le cadre du TP4 « Écran de détail produit »
(Bloc 2 – Compose UI). Elle affichera à terme un catalogue produit ; pour l'instant, elle contient
un écran de détail produit unique, construit avec les composants fondamentaux de Compose : `Text`,
`Button`, `Icon`, `Image`, `Card` et `TextField`.

## Écran de détail produit

L'écran assemble plusieurs composables réutilisables, chacun responsable d'une seule information :
une image produit, un en-tête (nom, marque, catégorie), une carte prix/remise, une note avec une
icône étoile, une carte de disponibilité (stock, livraison), une description, un champ garantie en
lecture seule et un bouton d'action.

## Aperçu

| Produit disponible | Produit indisponible |
|---|---|
| ![Smartphone Toto X, en stock](capture/SmartphoneToto.png) | ![Casque Audio Pulse, rupture de stock](capture/CasqueAudio.png) |

Les mêmes composables affichent ici deux produits totalement différents (nom, catégorie, prix,
stock, description), ce qui montre qu'ils sont bien paramétrés plutôt que figés sur un seul produit.

## Structure du projet

```
app/src/main/java/com/example/productexplorer/
└── MainActivity.kt
    ├── MainActivity              # Activity : thème + Scaffold
    ├── ProductDetailScreen        # assemble tous les blocs de l'écran
    ├── ProductHeader              # nom, marque, catégorie (MaterialTheme.typography)
    ├── ProductPriceCard           # Card : prix + remise
    ├── ProductImage               # Image + painterResource + contentDescription
    ├── ProductRating              # Row + Icon(Icons.Default.Star) + Text
    ├── ProductAvailabilityCard    # Card : stock + livraison
    ├── ProductDescription
    ├── ProductWarrantyField       # OutlinedTextField en lecture seule
    ├── AddToCartButton
    ├── ProductUi                  # données du produit
    ├── sampleProduct()            # produit en stock (previews + écran)
    └── sampleProductOutOfStock()  # produit en rupture de stock (preview)
```

## Previews

Deux `@Preview` sont disponibles dans `MainActivity.kt`, montrant chacune un produit différent :
`ProductDetailScreenPreview` (en stock) et `ProductDetailScreenOutOfStockPreview` (rupture de
stock) — ce sont les deux captures ci-dessus.
