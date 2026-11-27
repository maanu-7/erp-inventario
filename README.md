# erp-inventario · Módulo de Inventario (Grupo 2)

Módulo de **gestión de almacén** del ERP «Meseta»: catálogo de productos, categorías,
movimientos de stock (entrada / salida / ajuste), alertas de bajo mínimo y valoración del inventario.

| Parte | Tecnología | Puerto |
|---|---|---|
| `inventario-service` (API REST) | Java 21 · Spring Boot 3 · Maven | 8082 |
| `inventario-db` | MySQL 8.4 | 3306 (interno) |
| `inventario-app` (frontal) | Flutter 3 (Android + web con Nginx) | 8092 |

## Equipo y roles

| Miembro | Paquetes | Rol |
|---|---|---|
| [@maanu-7](https://github.com/maanu-7) | A (categorías y productos) + C (bajo mínimo, valoración, I8) | Coordinación · Integración |
| [@Pacitochocolatero](https://github.com/Pacitochocolatero) | B (movimientos de stock) + D (estadísticas, CORS, Docker) | Calidad y documentación · DevOps |

## Integraciones

| Código | Dirección | Endpoint |
|---|---|---|
| I2 | Ventas → Inventario | `GET /api/productos/{id}` · `POST /api/movimientos` |
| I4 | Compras → Inventario | `GET /api/productos/bajo-minimo` · `POST /api/movimientos` |
| I8 | Inventario → Compras | `GET /api/catalogo?productoId=` |

## Estructura del repositorio

```
erp-inventario/
├── inventario-service/   # Backend Spring Boot
├── inventario-app/       # App Flutter
├── docs/
│   ├── uml/              # Diagramas (PlantUML + imagen)
│   ├── openapi.yaml      # Contrato de la API
│   └── postman.json      # Colección Postman
├── docker-compose.yml    # (Sprint 2)
└── .env.example
```

## Cómo ejecutar

_Se completará en el Sprint 1 (local) y Sprint 2 (Docker)._

## Flujo de trabajo con Git

- `main`: versión estable, solo se actualiza mediante pull request.
- `develop`: integración del grupo.
- `feature/<nombre>`: una rama por tarea, que se fusiona en `develop` con pull request revisado por el compañero.
- Commits con Conventional Commits: `feat:`, `fix:`, `docs:`, `test:`, `chore:`…

## Uso de asistentes de IA

| Herramienta | Para qué |
|---|---|
| Claude | Explicación de la guía, planificación del trabajo y estructura inicial del repositorio. |
