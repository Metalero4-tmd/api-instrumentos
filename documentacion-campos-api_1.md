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
| `model` | Texto | ✅ | Modelo específico dentro de la marca. `null` cuando no aplica (ej: violín, armónica) |
| `price` | Número | ❌ | Precio de venta |
| `currency` | Texto | ❌ | Moneda del precio: `"USD"` para dólares, `"ARS"` para pesos argentinos |
| `photo` | Texto | ✅ | URL de la foto del producto. Usar Unsplash con formato `?w=400&q=80` al final |
| `type` | Texto | ❌ | Tipo de instrumento (Guitarra Eléctrica, Bajo Eléctrico, Batería, Piano Digital, etc.) |
| `category` | Texto | ❌ | Categoría general del instrumento |
| `available` | Booleano | ❌ | Si está disponible para la venta: `true` o `false` |
| `condition` | Texto | ❌ | Estado del producto: `"nuevo"` o `"usado"` |
| `color` | Texto | ❌ | Color del instrumento |
| `made` | Texto | ❌ | País de fabricación |
| `quantity` | Número | ❌ | Cantidad de unidades en stock. Si es `0`, `available` debe ser `false` |
| `weight` | Número | ✅ | Peso del instrumento en kilogramos |
| `sku` | Texto | ❌ | Código único interno del producto para inventario (ej: `"GTR-FEN-001"`) |
| `description` | Texto | ✅ | Descripción breve del producto |
| `vat` | Número | ❌ | IVA en porcentaje. En Argentina generalmente `21` |
| `discount` | Número | ✅ | Porcentaje de descuento aplicado. `null` si no tiene descuento |
| `installments` | Número | ✅ | Cantidad de cuotas disponibles. `null` si no tiene financiación |
| `tna` | Número | ✅ | Tasa Nominal Anual de financiación en porcentaje. `null` si no aplica |
| `warranty` | Texto | ✅ | Garantía del producto: `"6 meses"`, `"12 meses"`, `"2 años"`, etc. `null` si no tiene |

---

## 📦 Categorías sugeridas

| Valor | Instrumentos que incluye |
|-------|--------------------------|
| `"Cuerdas"` | Guitarra eléctrica, acústica, clásica, bajo, violín |
| `"Percusión"` | Batería acústica, batería electrónica |
| `"Teclas"` | Piano, piano digital, teclado, sintetizador, teclado MIDI |
| `"Vientos"` | Armónica, flauta, saxofón |

---

## 💱 Valores de moneda (`currency`)

| Valor | Descripción |
|-------|-------------|
| `"USD"` | Dólares estadounidenses |
| `"ARS"` | Pesos argentinos |

---

## 🧾 Ejemplo de registro completo

```json
{
  "id": 1,
  "brand": "Fender",
  "model": "Stratocaster",
  "price": 1500,
  "currency": "USD",
  "photo": "https://images.unsplash.com/photo-1510915361894-db8b60106cb1?w=400&q=80",
  "type": "Guitarra Eléctrica",
  "category": "Cuerdas",
  "available": true,
  "condition": "nuevo",
  "color": "Sunburst",
  "made": "Estados Unidos",
  "quantity": 5,
  "weight": 3.6,
  "sku": "GTR-FEN-001",
  "description": "Guitarra eléctrica de cuerpo sólido con tres micrófonos single coil. Ideal para rock, blues y pop.",
  "vat": 21,
  "discount": 10,
  "installments": 12,
  "tna": 45.5,
  "warranty": "12 meses"
}
```

---

## 🔄 Cómo actualizar el archivo

1. Modificá el `db.json` en VS Code
2. En la terminal:

```bash
git add .
git commit -m "actualizo campos del db.json"
git push
```

3. Render redeploya automáticamente en ~2 minutos

---

## 🔗 Endpoints útiles

| URL | Resultado |
|-----|-----------|
| `/instruments` | Todos los registros |
| `/instruments/1` | Registro con id 1 |
| `/instruments?_page=1&_limit=6` | Paginación: página 1, 6 por página |
| `/instruments?available=true` | Solo disponibles |
| `/instruments?condition=nuevo` | Solo productos nuevos |
| `/instruments?category=Cuerdas` | Solo instrumentos de cuerda |
| `/instruments?currency=USD` | Solo productos en dólares |

---

*Documentación generada durante el desarrollo del TP — UTN Full Stack 2026*
