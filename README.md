# EV Charging Station Optimal Location Selection Project



## **Overview**
This project focuses on determining the optimal locations for electric vehicle (EV) charging stations in the Michuhol district of Incheon, South Korea. The objective is to minimize travel and waiting times for EV users, improving accessibility and convenience.

The project combines geospatial analysis and optimization techniques, including genetic algorithms, to identify ideal locations for rapid EV charging stations.

## **Motivation**
Electric vehicles are key to reducing greenhouse gas emissions and combating climate change. However, the expansion of charging infrastructure is vital to support the increasing adoption of EVs. This study addresses the problem of identifying optimal locations for EV charging stations based on various criteria, including population density, proximity to existing stations, and points of interest.

## **Methodology**
The project integrates geospatial data processing and optimization using Python. It uses:
1. **Data Collection**: 
   - Spatial data of Michuhol district.
   - Existing charging station locations.
   - Population and building density data.

2. **Geospatial Analysis**:
   - Conversion of spatial data to uniform coordinate systems (EPSG:5179).
   - Visualization of current charging station locations and candidate points using `matplotlib` and `geopandas`.

3. **Optimization with Genetic Algorithms**:
   - **Initialization**: Random generation of candidate points within the Michuhol district.
   - **Evaluation**: Scoring candidate points based on proximity to population centers and existing stations.
   - **Selection**: Fitness-based selection of candidate points using a roulette-wheel approach.
   - **Crossover & Mutation**: Generate new candidates within the vicinity of high-performing points.
   - **Iteration**: Repeat until convergence or maximum iterations are reached.


## **Key Steps in the Code**
1. **Data Preparation**:
   - Load shapefile for Michuhol district.
   - Import existing charging station data and geocode it using `geopandas`.

2. **Random Point Generation**:
   - Create random candidate points within the district polygon using `shapely`.

3. **Fitness Evaluation**:
   - Calculate distances between candidate points and population centers.
   - Assign weights to criteria like distance, population density, and POIs.

4. **Visualization**:
   - Use `matplotlib` to visualize current and proposed charging station locations.

5. **Genetic Algorithm**:
   - Apply mutation and crossover to refine candidate points.

For detailed implementation and coding results, refer to the following Jupyter Notebook:

[Code Implementation: Genetic Algorithm for Optimal EV Charging Station Locations](https://github.com/limJhyeok/Comprehensive-design/blob/main/%EC%9C%A0%EC%A0%84%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9D%84%20%EC%9D%B4%EC%9A%A9%ED%95%9C%20%EC%A0%84%EA%B8%B0%EC%B0%A8%20%EC%B6%A9%EC%A0%84%EC%86%8C%20%EC%B5%9C%EC%A0%81%20%EC%9E%85%EC%A7%80%20%EC%84%A0%EC%A0%95.ipynb)

## **Usage**
### **Required Libraries**
Install the following Python libraries:
- `geopandas`
- `matplotlib`
- `pandas`
- `shapely`

### **Execution**
1. Place the required datasets (`.shp` files and Excel sheets) in the working directory.
2. Execute the Python script. The script will:
   - Visualize current and candidate station locations.
   - Perform genetic algorithm-based optimization.
   - Output the best candidate locations.

### **Input Data**
- **Spatial Data**: Michuhol district boundaries (`미추홀구.shp`).
- **Charging Station Data**: Existing EV charging station locations.
- **Normalized Data**: Factors affecting optimality (population, building density, etc.).

### **Outputs**
- Visualizations of candidate and selected charging station locations.
- Optimal station coordinates.

## **Results**
The algorithm identifies optimal locations for new EV charging stations, considering travel distance minimization and demand hotspots. Visual outputs include maps displaying the evolution of candidate points and final station placements.

## **Authors**
- Lim Jae Hyeok – Programming
- Yoon Ji Woong, Shin Woo Chul – Data Collection
- Lee Joo Yeon – Report Writing

**Institution**: Inha University  
**Year**: 2021

## References
1. 김지규."전기차 급속충전소의 최적 입지선정 연구(A study on Determine the Optimized Location for Electric Vehicle Fast Charging Station),” (석사학위, 서울시립대학교 대학원, 2021), 43
2. 진강규, 하주식."최적화기법으로서의 유전알고리즘과 그 응용 ( Genetic Algorithms as Optimisation Tools and Their Applications )."한국마린엔지니어링학회지21.2(1997):108-116.
3. StackExchange GIS. "Generating Random Coordinates in Multipolygon in Python." Available at: GIS StackExchange
4. 이원재, 김학영(2005), "Python 을 사용한 유전 알고리즘 구현", 제23회 한국정보처리학회 춘계학술발표대회 논문집 제12권 제1호 (2005. 5), pp.473~476
