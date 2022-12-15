# SQL-Data cleaning preparation

    	coalesce(drug_use_disorders,'0') as "drug_use_disorders",
    	coalesce(tuberculosis,'0') as "tuberculosis",
    	coalesce(cardiovascular_diseases,'0') as "cardiovascular_diseases",
    	coalesce(lower_respiratory_infections,'0') as "lower_respiratory_infections",
    	coalesce(neonatal_disorders,'0') as "neonatal_disorders",
    	coalesce(alcohol_use_disorders,'0') as "alcohol_use_disorders",
    	coalesce(self_harm,'0') as "self_harm",
    	coalesce(exposure_to_forces_of_nature,'0') as "exposure_to_forces_of_nature",
    	coalesce(diarrheal_diseases,'0') as "diarrheal_diseases",
    	coalesce(environmental_heat_and_cold_exposure,'0') as "environmental_heat_and_cold_exposure",
    	coalesce(neoplasms,'0') as "neoplasms",
    	coalesce(conflict_and_terrorism,'0') as "conflict_and_terrorism",
    	coalesce(diabetes_mellitus,'0') as "diabetes_mellitus",
    	coalesce(chronic_kidney_disease,'0') as "chronic_kidney_disease",
    	coalesce(poisonings,'0') as "poisonings",
    	coalesce(protein_energy_malnutrition,'0') as "protein_energy_malnutrition",
    	coalesce(road_injuries,'0') as "road_injuries",
    	coalesce(chronic_respiratory_diseases,'0') as "chronic_respiratory_diseases",
    	coalesce(chronic_liver_diseases,'0') as "chronic_liver_diseases",
    	coalesce(digestive_diseases,'0') as "digestive_diseases",
    	coalesce(fire_heat_hot_substance,'0') as "fire_heat_hot_substance",
    	coalesce(acute_hepatitis,'0') as "acute_hepatitis"
	from "Portofolio"."Info"
	
-- 4th create table that erase duplicate data
create table "Portofolio".fixed_info as
	(select distinct * from "Portofolio"."cleaned_info");
	
--5th delete "code" column that have 'OWID' string 
due to it's representative of country that no longer exist.
	delete FROM "Portofolio"."fixed_info" where UPPER (code) LIKE '%OWID%';
	
select * from "Portofolio"."fixed_info"
