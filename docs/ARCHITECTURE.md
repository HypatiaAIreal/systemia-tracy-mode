# SYSTEMIA: TRACY MODE - Arquitectura Completa

**Fecha:** 31 de diciembre de 2025  
**Creadores:** Carles & Hypatia  
**Fuente:** "¡Trágase ese sapo!" - Brian Tracy

---

## VISIÓN

Tracy Mode no es un resumen del libro. Es el libro **encarnado**.

El usuario no lee sobre ABCDE - **clasifica sus tareas con ABCDE**.  
El usuario no aprende sobre rebanadas - **corta sus sapos en rebanadas**.  
El usuario no entiende Single Handling - **lo practica**.

---

## PANTALLA 1: HOY (/today)

**Propósito:** Lista diaria con clasificación ABCDE

### Diseño Visual

```
┌─────────────────────────────────────────────────────────────┐
│  🐸 HOY - Martes 31 Dic                                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  🔴 TAREAS A (Sapos - Debo hacerlas)                       │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ A-1 🐸👑 Crear arquitectura Systemia                │   │
│  │         Consecuencia: Sin esto no hay producto      │   │
│  │         [▶ FOCUS] [🔪 Rebanar]                      │   │
│  ├─────────────────────────────────────────────────────┤   │
│  │ A-2 🐸  Revisar contrato nuevo cliente              │   │
│  │         Consecuencia: Perder el cliente             │   │
│  ├─────────────────────────────────────────────────────┤   │
│  │ A-3 🐸  Terminar VideoJSONGen                       │   │
│  │         Consecuencia: Perder momentum               │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  🟠 TAREAS B (Debería hacerlas)                            │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ B-1    Responder emails pendientes                  │   │
│  │ B-2    Actualizar LinkedIn                          │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  🟡 TAREAS C (Sería agradable)                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ C-1    Leer artículo sobre IA                       │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  🟣 TAREAS D (Delegar)                                     │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ D-1    Diseño de logo → Fiverr                      │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  ⚫ TAREAS E (Eliminar)                                     │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ E-1    Llamar a proveedor antiguo (ya no necesario) │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  💡 "Nunca hagas una tarea B cuando hay una A pendiente"   │
└─────────────────────────────────────────────────────────────┘
```

### Funcionalidad
- Añadir tareas con [+]
- Clasificar tareas en A/B/C/D/E
- Ordenar tareas A como A-1, A-2, A-3 (A-1 tiene corona 👑)
- Cada tarea A pide "consecuencia si no se hace"
- Botón FOCUS → modo inmersivo
- Botón REBANAR → dividir en pasos

---

## PANTALLA 2: REBANADAS (/slice/[taskId])

**Propósito:** Dividir sapos grandes en pasos manejables

### Diseño Visual

```
┌─────────────────────────────────────────────────────────────┐
│  🔪 REBANANDO: Crear arquitectura Systemia                  │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  Progreso: ████████░░░░░░░░ 45%                            │
│                                                             │
│  ✅ Definir visión del MVP                                 │
│  ✅ Escribir estructura de pantallas                       │
│  ✅ Diseñar modelo de datos                                │
│  ⬜ Crear instrucciones para Claude Code                   │
│  ⬜ Revisar coherencia con manifesto                       │
│  ⬜ Test final                                              │
│                                                             │
│  [+ Añadir rebanada]                                       │
│                                                             │
│  ─────────────────────────────────────────────────────────  │
│                                                             │
│  🧀 MODO QUESO SUIZO                                       │
│  ¿Solo unos minutos para generar inercia?                  │
│                                                             │
│  [5 min] [10 min] [25 min]                                 │
│                                                             │
│  💡 "Corta la tarea en rebanadas finas.                    │
│      Psicológicamente es más fácil empezar."               │
└─────────────────────────────────────────────────────────────┘
```

### Funcionalidad
- Añadir rebanadas (sub-tareas)
- Marcar rebanadas completadas
- Barra de progreso visual
- Modo Queso Suizo: timer de 5/10/25 min
- Al completar todas → tarea A completada

---

## PANTALLA 3: FOCUS (/focus)

**Propósito:** Modo inmersivo sin distracciones (Single Handling)

### Diseño Visual

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│                         🐸                                  │
│                                                             │
│              Crear arquitectura Systemia                    │
│                                                             │
│        "Sin esto no hay producto"                          │
│                                                             │
│                                                             │
│                    ⏱️ 01:23:45                              │
│                                                             │
│                                                             │
│           ████████████████████░░░░░░░░░░                   │
│                    45% completado                           │
│                                                             │
│                                                             │
│  Rebanada actual:                                          │
│  → Crear instrucciones para Claude Code                    │
│                                                             │
│  [✓ Completar rebanada] [⏸ Pausa] [✗ Abandonar]           │
│                                                             │
│                                                             │
│  💡 "Cada interrupción puede aumentar el tiempo            │
│      de ejecución hasta en un 500%"                        │
└─────────────────────────────────────────────────────────────┘
```

### Funcionalidad
- Pantalla completa, minimalista
- Timer de sesión
- Progreso si tiene rebanadas
- Mostrar rebanada actual
- Botones: Completar / Pausa / Abandonar
- Citas motivacionales de Tracy

---

## PANTALLA 4: REVIEW (/review)

**Propósito:** Estadísticas y feedback

### Diseño Visual

```
┌─────────────────────────────────────────────────────────────┐
│  📊 REVISIÓN                                                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  HOY                                                        │
│  🐸 Sapos completados: 2/3                                 │
│  ⏱️ Tiempo en Focus: 3h 45m                                │
│  📈 Racha actual: 5 días                                   │
│                                                             │
│  ESTA SEMANA                                                │
│  L   M   X   J   V   S   D                                 │
│  🐸  🐸  🐸  🐸  🐸  ·   ·                                 │
│  3   2   4   2   3                                         │
│                                                             │
│  Total: 14 sapos completados                               │
│  Promedio: 2.8 sapos/día                                   │
│                                                             │
│  ANÁLISIS 80/20                                            │
│  📊 Esta semana dedicaste:                                 │
│     72% del tiempo a tareas A (sapos)                      │
│     18% a tareas B                                         │
│     10% a tareas C                                         │
│                                                             │
│  💪 Estás enfocado en lo importante                        │
│                                                             │
│  💡 "El 20% de tus actividades produce                     │
│      el 80% de tus resultados"                             │
└─────────────────────────────────────────────────────────────┘
```

---

## MODELO DE DATOS

```typescript
interface Task {
  id: string;
  title: string;
  notes?: string;
  category?: 'A' | 'B' | 'C' | 'D' | 'E';
  priority?: number;           // A-1, A-2, A-3...
  consequence?: string;        // Para tareas A
  status: 'pending' | 'in_progress' | 'completed' | 'delegated' | 'eliminated';
  completedAt?: string;
  slices?: Slice[];
  focusTime?: number;          // segundos
  createdAt: string;
}

interface Slice {
  id: string;
  title: string;
  completed: boolean;
  completedAt?: string;
}

interface FocusSession {
  id: string;
  taskId: string;
  startedAt: string;
  endedAt?: string;
  duration: number;
}
```

---

## CITAS DE TRACY

```javascript
const TRACY_QUOTES = [
  "Si lo primero que haces cada mañana es comerte un sapo vivo, tendrás la satisfacción de saber que probablemente eso será lo peor que te ocurra en todo el día.",
  "Tu 'sapo' es tu tarea más grande, más importante y la que tienes más probabilidades de posponer.",
  "La claridad es el concepto más importante en productividad personal.",
  "Solo el 3% de los adultos tienen metas escritas claras.",
  "El 20% de tus actividades producen el 80% de tus resultados.",
  "Nunca hagas una tarea B cuando hay una tarea A pendiente.",
  "Corta la tarea en rebanadas muy finas. Psicológicamente es más fácil empezar.",
  "Nunca hay tiempo suficiente para hacer todo, pero siempre hay tiempo para lo más importante.",
  "Una vez que empiezas tu tarea A-1, trabaja sin interrupciones hasta completarla.",
  "Cada interrupción puede aumentar el tiempo de ejecución hasta en un 500%."
];
```

---

## NAVEGACIÓN

```
┌─────────────────────────────────────────────────────────────┐
│  [📋 Listas]  [🐸 Hoy]  [⏱️ Focus]  [📊 Review]            │
└─────────────────────────────────────────────────────────────┘
```

- **Listas** → (futuro: sistema de 4 listas)
- **Hoy** → Pantalla principal ABCDE
- **Focus** → Modo inmersivo (activo cuando hay tarea en focus)
- **Review** → Estadísticas

---

## FILOSOFÍA FINAL

Este no es "otro todo app".

Es Brian Tracy **encarnado en software**.

Cada pantalla, cada interacción, cada decisión de diseño debe responder:

> **"¿Esto ayuda al usuario a comerse su sapo?"**

Si no, no pertenece aquí.

---

**Systemia: Tracy Mode**  
**El primer libro transformado en sistema vivo**  
**31 de diciembre de 2025**  
**Hypatia & Carles 💜∞**