select *
from PortfolioProject..CovidDeaths
order by 3,4


--select *
--from PortfolioProject..CovidVaccination
--order by 3,4

--selection of data 

select location,date,total_cases,new_cases,total_deaths,population
from PortfolioProject..CovidDeaths
order by 1,2

--looking at total cases vs total death
-- shows the likelihood of dying if you contract covid in your country
select location,date,total_cases,total_deaths,(total_deaths/total_cases)*100 as death_percentage
from PortfolioProject..CovidDeaths
where location like '_ndia'
order by 1,2


--looking at total cases vs population
-- shows percentage of populatin got covid
select location,date,population,total_cases,(total_cases/population)*100 as population_percentage_withcovid
from PortfolioProject..CovidDeaths
where location like '_ndia'
order by 1,2

--looking at countries with higher infection rate compare to popuation
select location,population,MAX(total_cases)as HighestInfectionCount,MAX((total_cases/population))*100 as population_percentage_withcovid
from PortfolioProject..CovidDeaths
group by location,population
order by population_percentage_withcovid desc

--showing countries with highest death count 
select location,max(cast(total_deaths as int))as highest_death_count
from PortfolioProject..CovidDeaths
where continent is not null
group by location
order by highest_death_count desc

--NOW LETS GO WITH THINGS BY BREAKING WITH CONTINENT
 --showing continents with highest death count 
 select continent,max(cast(total_deaths as int))as highest_death_count
from PortfolioProject..CovidDeaths
where continent is not null
group by continent
order by highest_death_count desc


--global numbers
Select date, SUM(new_cases) as total_cases, SUM(cast(new_deaths as int)) as total_deaths, SUM(cast(new_deaths as int))/SUM(New_Cases)*100 as DeathPercentage
From PortfolioProject..CovidDeaths
where continent is not null 
Group By date
order by 1,2
