# 📋 Documentación de campos — API Instrumentos

> Referencia completa de todos los campos del `db.json`.  
> Campos en inglés, valores en español.  
> Última actualización: Junio 2026

---

## 📌 Listado de campos

| Campo | Tipo | Opcional | Descripción |
|-------|------|----------|-------------|
| `id` | Número | ❌ | Identificador único del producto. Lo usa JSON Server para las rutas (`/instruments/1`) |
| `brand` | Texto | ❌ | Marca del instrumento (Fender, Gibson, Yamaha, etc.) |
| `model` | Texto | ❌ | Modelo comercial completo (ej: `"Stratocaster Player Series HSS"`) |
| `price` | Número | ❌ | Precio actual de venta. Refleja el precio final con el descuento ya aplicado |
| `previousPrice` | Número | ✅ | Precio original antes del descuento (se muestra tachado). `null` si no tiene descuento |
| `currency` | Texto | ❌ | Moneda del precio: fijado en `"ARS"` para pesos argentinos |
| `photo` | Texto | ✅ | URL de la foto del producto (Unsplash con formato `?w=400&q=80`) |
| `type` | Texto | ❌ | Tipo de instrumento (Guitarra Eléctrica, Bajo Eléctrico, Batería, etc.) |
| `category` | Texto | ❌ | Categoría general del instrumento (`"Cuerdas"`, `"Percusión"`, `"Teclas"`, `"Vientos"`) |
| `available` | Booleano | ❌ | Disponibilidad de venta: `true` o `false` |
| `condition` | Texto | ❌ | Estado del producto: `"nuevo"` o `"usado"` |
| `color` | Texto | ❌ | Color del instrumento |
| `made` | Texto | ❌ | País de fabricación |
| `quantity` | Número | ❌ | Unidades en stock. Si es `0`, `available` pasa automáticamente a `false` |
| `weight` | Número | ✅ | Peso del instrumento en kilogramos |
| `sku` | Texto | ❌ | Código único de inventario (ej: `"GTR-FEN-001"`) |
| `description` | Texto | ✅ | Descripción breve del producto |
| `vat` | Número | ❌ | IVA en porcentaje (en Argentina se usa `21`) |
| `discount` | Número | ✅ | Porcentaje de descuento aplicado (ej: `10`). `null` si no tiene descuento |
| `installments` | Número | ✅ | Cantidad de cuotas disponibles. `null` si no tiene financiación |
| `tna` | Número | ✅ | Tasa Nominal Anual de financiación en porcentaje. `null` si no aplica |
| `warranty` | Texto | ✅ | Garantía del producto. `null` si no tiene |

---

## 💲 Lógica de precios con descuento (Pesos ARS)

| Situación | `price` (Valor Final) | `previousPrice` (Original) | `discount` (%) |
|-----------|-----------------------|----------------------------|----------------|
| Sin descuento | `$900000` | `null` | `null` |
| Con descuento (10%) | `$900000` | `$1000000` | `10` |