# BI SOFTPRO

**BI SOFTPRO** is an open-source business intelligence platform for creating interactive dashboards, visual analytics, and data-driven reports. It helps organizations transform raw data into actionable insights through charts, maps, KPI widgets, and advanced filtering.

## Key features

- Creating dashboards with the ability to customize their structure and add necessary widgets
- Creating widgets for displaying data with the ability to customize style, size, and appearance for ease of information perception
- Ability to expand the list of data for analytics and edit the structure of tables and charts
- Importing data from tables and databases, automating data export and user data entry
- Ability to import and export dashboards to save or transfer settings between different environments or for reuse

## Resources and documentation

- [https://bi.opengis.info](https://bi.opengis.info)

## Install & Usage

### 1. Install the package

```bash
npm install @opengis/bi
```

### 2. Import styles in your application entry or layout:

```ts
import '@opengis/bi/dist/style.css';
```

### 3. Register components

```vue
<script setup lang="ts">
import { defineAsyncComponent } from 'vue';
import '@opengis/bi/dist/style.css';

const VsDashboard = defineAsyncComponent(() =>
  import('@opengis/bi').then((m) => m.VsDashboard)
);
</script>

<template>
  <VsDashboard dashboard="sales" />
</template>
```

### 4. Register editor interface

```ts
// router.config.ts
export default [
  {
    path: '/bi.editor/:id?',
    component: () => import('@opengis/bi').then((m) => m.VsEditorPage),
  },
  {
    path: '/bi.dashboards',
    component: () => import('@opengis/bi').then((m) => m.AllDashboardsPage),
  },
];
```

### 5. Register API

```ts
import Fastify from 'fastify';
import biPlugin from '@opengis/bi/plugin.js';

const app = Fastify();
app.register(biPlugin, { prefix: '/api' });
```

## Contributions

We welcome contributions!
Feel free to open issues, suggest features, or submit pull requests.

## Licence

MIT
