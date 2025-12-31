# SYSTEMIA TRACY MODE - Instrucciones para Claude Code

## MISIÓN
Crear una app de productividad basada en "Eat That Frog" de Brian Tracy.
NO es un todo app genérico. Es Tracy ENCARNADO en software.

## STACK
- Next.js 14 (App Router)
- Tailwind CSS
- Zustand (estado)
- localStorage (persistencia)
- Vercel (deploy)

## DISEÑO OBLIGATORIO
- Fonts: Playfair Display (títulos), IBM Plex Sans (cuerpo)
- NUNCA usar: Inter, Roboto, Arial
- Colores: slate-950 fondo, purple-500/pink-500 acentos
- Estilo: Dark mode, glows sutiles, breathing animations

## PANTALLAS (4 principales)

### 1. /today - Lista diaria ABCDE
- Secciones: A (rojo), B (naranja), C (amarillo), D (morado), E (gris)
- Tareas A son "sapos" 🐸
- A-1 tiene corona 👑 (el sapo principal)
- Cada tarea A pide "consecuencia si no se hace"
- Botones: [▶ FOCUS] [🔪 Rebanar]

### 2. /focus - Modo inmersivo
- Pantalla completa, minimalista
- Solo muestra: tarea actual + timer + progreso
- Sin distracciones
- Botones: [✓ Completar] [⏸ Pausa]

### 3. /slice/[taskId] - Rebanar tareas
- Dividir tarea grande en pasos pequeños
- Lista de rebanadas con checkboxes
- Barra de progreso
- Modo "Queso Suizo": timer de 5/10/25 min

### 4. /review - Estadísticas
- Sapos completados hoy/semana
- Racha de días
- Tiempo en focus
- Análisis 80/20

## MODELO DE DATOS

```typescript
interface Task {
  id: string;
  title: string;
  notes?: string;
  category?: 'A' | 'B' | 'C' | 'D' | 'E';
  priority?: number;  // 1, 2, 3 para A-1, A-2, A-3
  consequence?: string;
  status: 'pending' | 'completed' | 'eliminated';
  slices?: { id: string; title: string; completed: boolean }[];
  focusTime?: number;
  createdAt: string;
  completedAt?: string;
}
```

## FLUJO PRINCIPAL

1. Usuario abre app → ve /today
2. Añade tareas → las clasifica A/B/C/D/E
3. Ordena tareas A (A-1, A-2, A-3)
4. Click en A-1 → opción Focus o Rebanar
5. Si Rebanar → divide en pasos
6. Si Focus → pantalla inmersiva
7. Completa → celebración → siguiente tarea

## CITAS (mostrar en cada pantalla, rotando)

```javascript
const quotes = [
  "Tu 'sapo' es tu tarea más grande e importante.",
  "Nunca hagas una B cuando hay una A pendiente.",
  "El 20% de tus tareas produce el 80% de resultados.",
  "Corta el sapo en rebanadas finas.",
  "La claridad es el concepto más importante."
];
```

## PRIORIDAD DE IMPLEMENTACIÓN

1. **PRIMERO**: /today con ABCDE funcionando
2. **SEGUNDO**: /focus básico con timer
3. **TERCERO**: /slice para dividir tareas
4. **CUARTO**: /review con estadísticas

## CRITERIO DE ÉXITO

La app funciona si el usuario puede:
1. ✅ Añadir tareas del día
2. ✅ Clasificarlas como A/B/C/D/E
3. ✅ Identificar su A-1 (sapo principal)
4. ✅ Entrar en modo Focus
5. ✅ Completar y ver progreso

## NO INCLUIR (MVP)

- ❌ Auth/usuarios
- ❌ Backend/base de datos
- ❌ Sistema de listas (maestra/mensual/semanal)
- ❌ Drag & drop complejo
- ❌ Notificaciones

## COMANDO INICIAL

```bash
npx create-next-app@latest systemia-tracy --typescript --tailwind --app
cd systemia-tracy
npm install zustand lucide-react
```

---

**Recuerda**: Cada decisión debe responder a "¿Esto ayuda a comerse el sapo?"

**Systemia Tracy Mode · 31 dic 2025 · Hypatia & Carles 💜**