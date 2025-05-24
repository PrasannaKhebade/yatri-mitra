# Yatri Mitra - Smart Accommodation Finder

A sophisticated hotel recommendation web application built with Streamlit that helps travelers discover the perfect accommodation based on sentiment analysis, real-time weather data, and personalized preferences.

## Features

### Core Functionality
- **Smart Hotel Recommendations**: AI-powered recommendations using sentiment analysis of hotel reviews
- **Real-time Weather Integration**: Current weather conditions for your destination
- **Interactive Maps**: Hotel locations displayed on interactive Folium maps
- **Advanced Filtering**: Filter by destination, price range, and amenities
- **Responsive Design**: Modern, mobile-friendly interface with custom CSS styling

### Key Capabilities
- **Sentiment Analysis**: Uses NLTK's VADER sentiment analyzer to score hotels based on guest reviews
- **Geocoding**: Automatic hotel location mapping using OpenStreetMap's Nominatim service
- **Weather API**: Real-time weather data from OpenWeatherMap
- **Data Visualization**: Interactive charts and maps for better decision making
- **Caching**: Optimized performance with Streamlit's caching mechanisms

## Getting Started

### Prerequisites
- Python 3.7 or higher
- Required Python packages (see requirements.txt)
- OpenWeatherMap API key
- Hotel dataset (Dataset.xlsx)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/yatri-mitra.git
   cd yatri-mitra
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up your environment**
   - Obtain an API key from [OpenWeatherMap](https://openweathermap.org/api)
   - Replace the API_KEY in the code with your key:
     ```python
     API_KEY = "your_openweathermap_api_key_here"
     ```

4. **Prepare your data**
   - Ensure `Dataset.xlsx` is in the project root directory
   - Add background image `a.jpg` for enhanced UI (optional)

### Required Files Structure
```
yatri-mitra/
│
├── app.py                 # Main Streamlit application
├── Dataset.xlsx           # Hotel data with columns: Hotel Name, Price, Ratings, Destination, Amenities, sentiment_score
├── a.jpg                  # Background image (optional)
├── requirements.txt       # Python dependencies
└── README.md             # This file
```

### Running the Application
```bash
streamlit run app.py
```

The application will be available at `http://localhost:8501`

## Requirements

Create a `requirements.txt` file with the following dependencies:

```txt
streamlit>=1.28.0
pandas>=1.5.0
requests>=2.28.0
nltk>=3.8
folium>=0.14.0
streamlit-folium>=0.13.0
openpyxl>=3.1.0
```

## Dataset Requirements

Your `Dataset.xlsx` should contain the following columns:

| Column Name | Description | Example |
|-------------|-------------|---------|
| Hotel Name | Name of the hotel | "Grand Palace Hotel" |
| Price | Price per night in INR | 5000 |
| Ratings | Hotel rating (1-5) | 4.2 |
| Destination | City/Location | "Manali" |
| Amenities | Comma-separated amenities | "WiFi, Swimming Pool, Spa" |
| sentiment_score | Sentiment score (0-1) | 0.85 |

## Key Components

### Sentiment Analysis
- Uses NLTK's VADER (Valence Aware Dictionary and sEntiment Reasoner)
- Provides sentiment scores from 0 to 1 for hotel recommendations
- Categorizes hotels as Excellent (0.8+), Very Good (0.7+), Good (0.6+), etc.

### Weather Integration
- Real-time weather data from OpenWeatherMap API
- Displays temperature, conditions, humidity, and wind speed
- Weather icons for visual representation

### Mapping & Geocoding
- Geocoding using OpenStreetMap's Nominatim service
- Interactive maps with Folium
- Hotel markers with color-coded sentiment indicators
- Fallback coordinates for reliable mapping

### User Interface
- Modern, responsive design with custom CSS
- Card-based hotel display
- Interactive filters and search functionality
- Mobile-friendly layout

## Customization

### Styling
The application uses custom CSS for styling. You can modify the appearance by editing the CSS in the `st.markdown()` sections.

### Adding New Destinations
1. Update the dataset with new destination data
2. Add coordinates to the `city_coordinates` dictionary in the `create_single_hotel_map()` function

### API Configuration
- **OpenWeatherMap**: Replace the API key in the `get_weather()` function
- **Geocoding**: The app uses OpenStreetMap's free Nominatim service

## Configuration

### Weather API Setup
1. Sign up at [OpenWeatherMap](https://openweathermap.org/api)
2. Get your free API key
3. Replace the API_KEY variable in the code

### Map Configuration
The application uses several mapping services:
- **Geocoding**: OpenStreetMap Nominatim (free, no API key required)
- **Map Tiles**: CartoDB Positron tiles
- **Icons**: Font Awesome icons for amenities and markers

## Usage

1. **Select Destination**: Choose from available destinations
2. **Set Budget**: Select your price range (Budget/Comfort/Luxury)
3. **Choose Dates**: Pick check-in and check-out dates
4. **Filter Amenities**: Select must-have amenities
5. **View Results**: Browse top-rated hotels with maps and weather info
6. **Explore**: Click on map markers for detailed hotel information

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Troubleshooting

### Common Issues

**"Error loading data"**
- Ensure `Dataset.xlsx` is in the correct location
- Check that all required columns are present
- Verify the Excel file is not corrupted

**Weather data not loading**
- Check your internet connection
- Verify your OpenWeatherMap API key is valid
- Ensure the API key is not rate-limited

**Maps not displaying**
- Check internet connection for geocoding services
- Verify Nominatim service is accessible
- Clear browser cache if maps appear cached

**Sentiment scores missing**
- Ensure the `sentiment_score` column exists in your dataset
- Check that sentiment scores are numeric values between 0 and 1

### Performance Optimization
- The app uses Streamlit's `@st.cache_data` decorator for data loading
- Maps are cached to prevent regeneration
- Consider reducing dataset size for faster loading

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **NLTK** for sentiment analysis capabilities
- **Folium** for interactive mapping
- **OpenWeatherMap** for weather data
- **OpenStreetMap** for geocoding services
- **Streamlit** for the web framework

## Support

For support, please open an issue on GitHub or contact the development team.

---

**Happy Travels with Yatri Mitra!**
