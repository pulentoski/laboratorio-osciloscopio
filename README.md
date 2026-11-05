# Laboratorio Virtual · Generador de Funciones y Osciloscopio

Simulador web pedagógico de un banco de pruebas: generador de funciones de 2 canales, osciloscopio analógico de 2 canales y analizador de espectro, controlados con perillas y botones como en un equipo real. Incluye guía de uso y ejercicios prácticos con corrección automática.

Todo funciona en un solo archivo (`index.html`), sin dependencias ni servidor.

## Características

**Generador de funciones**
- Ondas senoidal, triangular, cuadrada y diente de sierra.
- Frecuencia 1 Hz – 1 MHz (ajuste grueso y fino), amplitud 10 mV – 15 Vpp, offset ±10 V, fase 0–360°.
- Valores editables escribiendo sobre el display (`2.5k`, `500m`, `1M`).

**Osciloscopio**
- VOLTS/DIV (10 mV – 20 V) y TIME/DIV (0,1 µs – 0,2 s).
- Acoplamiento AC / DC / GND, con filtro pasa-altos real en AC (~10 Hz).
- Modos CH1, CH2, DUAL, ADD, X-Y (Lissajous) e inversión de CH2.
- Disparo con nivel, fuente, pendiente y modo AUTO / NORM.
- Barrido lento visible, persistencia y resplandor del fósforo, enfoque, intensidad y grosor de trazo.
- Lectura de escalas en pantalla y medidas automáticas (Vpp, máx, mín, f, T).

**Analizador de espectro**
- CENTER, SPAN, FULL SPAN, REF LEVEL con atenuación automática, escala en dB/div y RBW (auto o manual).
- Marcador con búsqueda de pico, siguiente pico, MKR → CF y marcador delta (Δf y dB).
- Traza WRITE / MAX HOLD / AVG, piso de ruido dependiente de RBW y atenuación, tiempo de barrido realista.
- Espectro calculado por serie de Fourier de cada forma de onda, con distorsión armónica del generador y fuga del oscilador local en 0 Hz.

**Pedagogía**
- Nombres de controles en inglés con su traducción al español y ayuda emergente.
- Guía: lectura de pantalla, fórmulas, tabla de cada control, receta de 6 pasos, problemas frecuentes y sección del analizador de espectro (dBm, armónicos, RBW).
- 15 ejercicios (básico a avanzado; 6 de ellos con el analizador de espectro) que configuran los equipos automáticamente, con preguntas corregidas al instante y resolución paso a paso. Algunos ocultan el generador para medir una señal desconocida.

## Estructura

```
├── index.html     Aplicación completa (HTML + CSS + JS)
├── favicon.svg    Ícono del sitio
├── _headers       Cabeceras HTTP para Cloudflare Pages
├── LICENSE        Licencia MIT
└── README.md
```

## Uso local

Abrir `index.html` en cualquier navegador moderno (Chrome, Firefox, Edge, Safari).

## Publicar en Cloudflare Pages (desde GitHub)

1. Subir este repositorio a GitHub:
   ```bash
   git remote add origin https://github.com/<usuario>/laboratorio-osciloscopio.git
   git push -u origin main
   ```
2. En el dashboard de Cloudflare: **Workers & Pages** → **Create application** → pestaña **Pages** → **Connect to Git**.
3. Autorizar GitHub y elegir el repositorio.
4. Configuración de build:
   - Framework preset: `None`
   - Build command: *(vacío)*
   - Build output directory: `/`
5. **Save and Deploy**. El sitio queda en `https://<proyecto>.pages.dev`.

Cada `git push` a `main` publica automáticamente la nueva versión.

## Insertar en Moodle u otra página

```html
<iframe src="https://<proyecto>.pages.dev" width="100%" height="900" style="border:none"></iframe>
```

## Licencia

MIT. Ver [LICENSE](LICENSE).
