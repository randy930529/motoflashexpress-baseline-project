                ┌───────────────────────┐
                │   Web / Mobile App    │
                │  (Frontend clientes)  │
                └───────────▲───────────┘
                            │
                            │ REST API
                            │
                ┌───────────┴───────────┐
                │       API Layer        │
                │ (Servicios REST, auth) │
                └───────────▲───────────┘
                            │
                            │
                ┌───────────┴───────────┐
                │   Central Database     │
                │ (Pedidos, usuarios,    │
                │  pagos, logística)     │
                └───────────▲───────────┘
                            │
                            │
                ┌───────────┴───────────┐
                │ Shared Logistics Module│
                │ (Asignación riders,    │
                │  tracking entregas)    │
                └───────────▲───────────┘
                            │
                            │
                ┌───────────┴───────────┐
                │   Internal Ops System  │
                │ (Gestión interna,      │
                │  control de pagos)     │
                └────────────────────────┘
