# EcoEyes - Global Greenhouse Emissions

A simple Astro web application that displays greenhouse gas emissions data from countries around the world. This project visualizes CO₂ emissions data by country to help understand each nation's contribution to global climate change.

![EcoEyes Screenshot](https://github.com/user-attachments/assets/21a2c41d-2d40-494d-a249-b3304d6b2c62)

## Features

- 🌍 **Global Emissions Data**: Displays CO₂ emissions data from countries worldwide
- 📊 **Statistics Dashboard**: Shows total countries, total emissions, and average emissions
- 🎨 **Responsive Design**: Clean, eco-friendly green theme that works on all devices
- 🏗️ **Built with Astro**: Fast, modern static site generator with server-side rendering
- 📡 **World Bank API**: Fetches data from the World Bank's public API (with fallback mock data)
- 🔧 **TypeScript**: Fully typed for better development experience

## Data Source

This application uses the [World Bank Open Data API](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392) to fetch CO₂ emissions data. The specific indicator used is `EN.ATM.CO2E.KT` (CO2 emissions in kilotons).

- **Data Year**: 2020 (most recent comprehensive data available)
- **Format**: CO₂ emissions measured in kilotons
- **Coverage**: Countries and territories worldwide
- **Fallback**: Sample data from top emitting countries when API is unavailable

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn package manager

### Installation

1. Clone the repository:
```bash
git clone https://github.com/pratt33k/ecoeyes.git
cd ecoeyes
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and visit `http://localhost:4321`

### Building for Production

```bash
npm run build
```

The built site will be in the `dist/` directory.

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run astro` - Run Astro CLI commands

## Project Structure

```
├── src/
│   ├── components/
│   │   └── EmissionsData.astro    # Main data display component
│   ├── data/
│   │   └── mockData.ts            # Fallback sample data
│   ├── layouts/
│   │   └── Layout.astro           # Base page layout
│   └── pages/
│       └── index.astro            # Main page with API integration
├── public/
│   └── favicon.svg                # Site icon
├── astro.config.mjs               # Astro configuration
├── package.json                   # Dependencies and scripts
└── tsconfig.json                  # TypeScript configuration
```

## API Integration

The application fetches data server-side during build/render time to avoid CORS issues:

```typescript
// Fetches from World Bank API
const response = await fetch('https://api.worldbank.org/v2/country/all/indicator/EN.ATM.CO2E.KT?format=json&date=2020&per_page=300');
```

If the API is unavailable, the app gracefully falls back to displaying sample data from major emitting countries.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Data provided by [The World Bank](https://data.worldbank.org/)
- Built with [Astro](https://astro.build/)
- Inspired by the need for climate awareness and data transparency