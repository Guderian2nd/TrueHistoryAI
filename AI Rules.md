# Global Rules


IF DeltaFightingUnitNum is DeltaUnitHigh THEN NeedFightingUnit is Low

IF DeltaFightingUnitNum is DeltaUnitMedium THEN NeedFightingUnit is Medium

IF DeltaFightingUnitNum is DeltaUnitLow THEN NeedFightingUnit is High

IF RemainingGold is RemainGoldLow THEN NeedFightingUnit is VeryLow

IF RemainingLabor is RemainLaborLow THEN NeedFightingUnit is VeryLow

IF NeedFightingUnit is High THEN BuildFightingUnit is High

IF NeedFightingUnit is Medium THEN BuildFightingUnit is Medium

IF NeedFightingUnit is Low THEN BuildFightingUnit is Low

IF NeedFightingUnit is VeryLow THEN BuildFightingUnit is VeryLow


IF DeltaCityNum is CityHigh THEN NeedCity is Low

IF DeltaCityNum is CityMedium THEN NeedCity is Medium

IF DeltaCityNum is CityLow THEN NeedCity is High

IF NeedCity is Low THEN NeedPioneer is VeryLow

IF NeedCity is High THEN NeedPioneer is VeryHigh

IF RemainingGold is RemainGoldLow THEN NeedPioneer is VeryLow

IF RemainingLabor is RemainLaborLow THEN NeedPioneer is VeryLow

If NeedCity is High THEN BuildCityCenter is High

If NeedCity is Low THEN BuildCityCenter is Low

If NeedPioneer is High THEN BuildPioneer is High

If NeedPioneer is Low THEN BuildPioneer is Low




IF EnemyFightingUnitNum is FightingUnitNumHigh THEN BuildMilitaryBuilding is High

IF EnemyFightingUnitNum is FightingUnitNumMedium THEN BuildMilitaryBuilding is Medium

IF EnemyFightingUnitNum is FightingUnitNumLow THEN BuildMilitaryBuilding is Low

IF AllMyUnitEnemDist is EnemDistLow THEN BuildMilitaryBuilding is High

IF AllMyUnitEnemDist is EnemDistHigh THEN BuildMilitaryBuilding is Low

IF RemainingGold is RemainGoldLow THEN BuildMilitaryBuilding is VeryLow

IF RemainingLabor is RemainLaborLow THEN BuildMilitaryBuilding is VeryLow




IF DeltaHappyGoal is DeltaHappyGoalHigh THEN SetEconInvesttoFull is VeryHigh

IF DeltaHappyGoal is DeltaHappyGoalHigh THEN SetEconInvesttoDouble is VeryLow

IF DeltaHappyGoal is DeltaHappyGoalLow THEN SetEconInvesttoDouble is VeryHigh

IF DeltaHappyGoal is DeltaHappyGoalLow THEN SetEconInvesttoFull is VeryLow


IF NeedLabor is High THEN HappinessGoal is HVeryHigh

IF NeedGold is VeryHigh THEN HappinessGoal is HLow

IF RemainingGold is VeryLow OR RemainingGold is Low THEN NeedGold is VeryHigh

IF RemainingGold is RemainGoldVeryHigh OR RemainingGold is RemainGoldHigh THEN NeedGold is VeryLow

IF RemainingGold is RemainGoldMedium THEN NeedGold is Medium

ibid. for Labor


IF TechLost is TechLostHigh THEN NeedTech is VeryHigh

IF TechLost is TechLostMedium THEN NeedTech is High

IF TechLost is TechLostLow THEN NeedTech is Medium

IF Tech is TechHigh THEN NeedTech is Low

IF Tech is TechNormal THEN NeedTech is Medium

IF Tech is TechLow THEN NeedTech is High

IF NeedGold is VeryHigh THEN NeedTech is VeryLow

IF NeedTech is High THEN TechInvest is THigh

IF NeedTech is Medium THEN TechInvest is TMedium

IF NeedTech is Low THEN TechInvest is TLow


IF DmgUnitNum is UnitNumHigh THEN NeedLogistics is High

IF DmgUnitNum is UnitNumMedium THEN NeedLogistics is Medium

IF DmgUnitNum is UnitNumLow THEN NeedLogistics is Low

IF DmgUnitNum is UnitNumVeryLow THEN NeedLogistics is VeryLow

IF RemainingLabor is RemainLaborHigh THEN NeedLogistics is Medium

IF NeedLogistics is High THEN Logistics is LHigh

IF NeedLogistics is Medium THEN Logistics is LMedium

IF NeedLogistics is Low THEN Logistics is LLow

IF NeedLogistics is VeryLow THEN Logistics is LVeryLow

## Variables

DeltaFightingUnitNum : 적의 유닛 갯수 & 도시 갯수 와 내 현재 유닛 갯수와의 차이
* (-infinity,+infinity)
* Def. (My Fighting Unit Number) - (1.5 × Enemy Fighting Unit Number + Enemy City Number)


RemainingGold: 턴당 금 생산량의 여유로운 정도
* (-infinity, +infinity)
* Def. 현재 남아있는 턴당 금(즉 사용되지 않고 있는)

RemainingLabor: 턴당 노동력의 여유로운 정도
* [0, +infinity)
* Def. 현재 남아있는 턴당 노동력(즉 사용되지 않고 있는)

NeedFightingUnit: 전투유닛이 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

BuildFightingUnit: 전투유닛을 실제로 생산할 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

DeltaCityNum: 적 도시 갯수와 내 잠재적 도시 갯수와의 차이
* (-infinity, +infinity)
* Def. (My City Number + My Pioneer Number) - (1.5 × Enemy City Number)

NeedCity: 도시가 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

NeedPioneer: 개척자가 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]


BuildCityCenter: 실제로 도시를 생산할 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

BuildPioneer: 실제로 개척자를 생산할 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

EnemyFightingUnitNum: 적 전투유닛의 갯수
* [0, +infinity)
* Def. 적 전투유닛의 갯수

 AllMyUnitEnemDist: 얼마나 적 군대와 내 군대가 가까운지의 정도
 * [0, +infinity)
* Def. 각 개별적 내 전투유닛들과 가장 가까운 적 전투유닛과의 거리의 평균

DeltaHappyGoal: 내 목표행복도(Happiness Goal)와 현재 행복도와의 차이 정도
* [-200, +200]
* Def. HappinessGoal - Happy

SetEconInvesttoFull: 민간계투자량을 100%로 하고싶은 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

SetEconInvesttoDouble: 민간계투자량을 200%로 하고싶은 정도
 * (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

HappinessGoal: 목표행복도
* [-100,100]
* Def. 목표행복도
 
Gold: 현재 금 보유량
* [0, +infinity)
* Def. 현재 금 보유량

Tech: 현재 기술력 보유량
* ibid.

Labor: 현재 노동력 보유량
* ibid.

Happy: 현재 행복도
* [-100,+100]
* Def. 현재 행복도

NeedGold: 금이 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

NeedLabor: 노동력이 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

NeedTech: 기술력이 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

TechLost: 기술력이 정복등으로 사라진량
* [0,+infinity)
* Def. 바로전 적국 Subturn때 내가 정복등으로 잃어버린 기술력의 량

TechInvest: 기술계 투자량
* [0,2]
* Def. 기술계 투자량

DmgUnitNum: 피해를 입은 유닛의 전체 유닛중 비율
* [0, 1]
* Def. 피해를 입은 유닛의 갯수/총 유닛의 갯수

NeedLogistics: 병참이 필요한 정도
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

Logistics: 병참 투자율
* [0,1]
* Def. 병참 투자율



## Sets

DeltaUnitHigh: [0,50,+infinity]

DeltaUnitMedium: [-70, -50, 50, 70]

DeltaUnitLow: [-infinity, -50, 0]


RemainGoldVeryHigh: [500,1000,+infinity]

RemainGoldHigh: [0, 500,1000,1500]

RemainGoldMedium: [-750,-250,250,750]

RemainGoldLow: [-1500,-1000,-500,0]

RemainGoldVeryLow: [-infinity,-1000,-500]

RemainLaborVeryHigh: [500,1000,+infinity]

RemainLaborHigh: [250, 500,750,1000]

RemainLaborMedium: [50,100,250,500]

RemainLaborLow: <0,0,50,100]

RemainLaborVeryLow: [-infinity,-1000,-500]


CityHigh: [+10,+20,+infinity]

CityMedium: [-20,-10,+10,+20]

CityLow: [-infinity,-20,-10]


FightingUnitNumHigh: [25,50,+infinity]

FightingUnitNumMedium:[0,25,50,75]

FightingUnitNumLow:[-infinity,0,25]

EnemDistLow: [-infinity, 3,5]

EnemDistHigh: [4,6,+infinity]


DeltaHappyGoalHigh: <0,0,+infinity>

DeltaHappyGoalLow: <-infinity,0,0>


HVeryHigh: [50,75,100,100>

HHigh: [25,50,75,100]

HMedium: [-50,-25,25,50]

HLow: [-100,-75,-50,-25]

HVeryLow: <-100,-100,-75,-50]


TechLostHigh: [2500,5000,+infinity]

TechLostMedium: [0,2500,5000,7500]

TechLostLow: <0,0,2500,5000]


GoldHigh: [2500, 5000, +infinity]

GoldNormal: [0,2500,5000,7500]

GoldLow: <0,0,2500,5000]


TechHigh: [10000,20000,+infinity]

TechNormal: [5000,10000,20000,25000]

TechLow: <0,0,5000,10000]


LaborHigh: [1000,2000,+infinity]

LaborNormal: [250,500,1000,1500]

LaborLow: [0,100,250,500]


THigh: [1,1.5,2,2>

TMedium: [0.5,0.75,1.25,1.5]

TLow: <0,0,0.5,1]


UnitNumHigh: [0.5,0.75,1,1>

UnitNumMedium: [0.2,0.4,0.6,0.8]

UnitNumLow: [0.05,0.1,0.2,0.25]

UnitNumVeryLo




## IF

MyUnitHP is HPHigh

MyUnitHP is HPLow

EnemyUnitHP is HPHigh

EnemyUnitHP is HPLow

EnemyCityHP is HPHigh

EnemyCityHP is HPLow


SpotDamage is DamageHigh

SpotDeal is DealHigh

SpotEnemDist is DistEnemHigh

SpotEnemDist is DistEnemLow

SpotMyCityDist is DistMyCityHigh

SpotMyCityDist is DistMyCityLow


SkillEffect is DamageEnemy

SkillEffect is RestoreAP

SkillEffect is RestoreHP

SkillEffect is Buff


SkillTargetHP is HPHigh

SkillTargetHP is HPLow

SkillTargetSpot is DamageHigh

SkillTargetSpot is DealHigh


DeltaFightingUnitNum is DeltaUnitHigh

DeltaFightingUnitNum is DeltaUnitLow


NeedFightingUnit is High

NeedFightingUnit is Low


DeltaCityNum is DeltaCityHigh

DeltaCityNum is DeltaCityLow


RemainingGold is RemainGoldHigh

RemainingGold is RemainGoldLow

RemainingLabor is RemainLaborHigh

RemainingLabor is RemainLaborLow


BuildingProdResource is Gold/Labor/Tech/Happy


Gold is GoldHigh

Gold is GoldMedium

Gold is GoldLow

마찬가지

EnemyFightingUnitNum is FightingUnitNumHigh


AllMyUnitEnemDist is EnemDistHigh ... 


MyUnit is FightingUnit

MyUnit is Pioneer


CityatSpotRsrcBuildingNum is RsrcBuildingNumHigh

CityatSpotRsrcBuildingNum is RsrcBuildingNumLow


SpotRsrcBuildingNear is SpotRsrcBuildingNearHigh

SpotRsrcBuildingNear is SpotRsrcBuildingNearLow


SpotMyUnitDist is MyUnitDistHigh

SpotMyUnitDist is MyUnitDistLow


QuestReward is UltimateWeaponRsrc

QuestReward is MilitarySpecRsrc

QuestDisplay is DisplayPeriodLow

QuestDue is DueLow

QuestReward is Gold/Labor/Happy/Tech

QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff


DeltaHappyGoal is DeltaHappyGoalHigh

DeltaHappyGoal is DeltaHappyGoalLow


NeedLabor is High

NeedLabor is Medium

NeedLabor is Low

NeedGold is VeryHigh

NeedGold is High

NeedGold is Medium

NeedGold is Low


Tech is TechHigh

Tech is TechMedium

Tech is TechLow


NeedTech is High

NeedTech is Medium

NeedTech is Low


DmgUnitNum is High

DmgUnitNum is Medium

DmgUnitNum is Low


NeedLogistics is High

NeedLogistics is Medium

NeedLogistics is Low



## THEN

AttackUnit is VeryHigh

AttackUnit is High

AttackUnit is Medium

AttackUnit is Low

AttackUnit is VeryLow


MoveFightingUnittoSpot is VeryHigh

MoveFightingUnittoSpot is High

MoveFightingUnittoSpot is Medium

MoveFightingUnittoSpot is Low

MoveFightingUnittoSpot is VeryLow


MovePioneertoSpot is VeryHigh

MovePioneertoSpot is High

MovePioneertoSpot is Medium

MovePioneertoSpot is Low

MovePioneertoSpot is VeryLow


UseSkill is VeryHigh

UseSkill is High

UseSkill is Medium

UseSkill is Low

UseSkill is VeryLow


BuildFightingUnit is VeryHigh

BuildFightingUnit is High

BuildFightingUnit is Medium

BuildFightingUnit is Low

BuildFightingUnit is VeryLow


BuildResourceBuilding is VeryHigh

BuildResourceBuilding is High

BuildResourceBuilding is Medium

BuildResourceBuilding is Low

BuildResourceBuilding is VeryLow


BuildMilitaryBuilding is VeryHigh

BuildMilitaryBuilding is High

BuildMilitaryBuilding is Medium

BuildMilitaryBuilding is Low

BuildMilitaryBuilding is VeryLow


DeployUnittoCity is VeryHigh

DeployUnittoCity is High

DeployUnittoCity is Medium

DeployUnittoCity is Low

DeployUnittoCity is VeryLow


DeployInteriorBuildingtoCity is VeryHigh

DeployInteriorBuildingtoCity is High

DeployInteriorBuildingtoCity is Medium

DeployInteriorBuildingtoCity is Low

DeployInteriorBuildingtoCity is VeryLow


DeployTileResourceBuildingtoSpot is VeryHigh

DeployTileResourceBuildingtoSpot is High

DeployTileResourceBuildingtoSpot is Medium

DeployTileResourceBuildingtoSpot is Low

DeployTileResourceBuildingtoSpot is VeryLow


DeployMilitaryBuildingtoSpot is VeryHigh

DeployMilitaryBuildingtoSpot is High

DeployMilitaryBuildingtoSpot is Medium

DeployMilitaryBuildingtoSpot is Low

DeployMilitaryBuildingtoSpot is VeryLow


DeployCitytoPioneer is VeryHigh

DeployCitytoPioneer is High

DeployCitytoPioneer is Medium

DeployCitytoPioneer is Low

DeployCitytoPioneer is VeryLow


AcceptQuest is VeryHigh

AcceptQuest is High

AcceptQuest is Medium

AcceptQuest is Low

AcceptQuest is VeryLow


HappinessGoal is HVeryHigh

HappinessGoal is HHigh

HappinessGoal is HMedium

HappinessGoal is HLow

HappinessGoal is HVeryLow


SetEconInvesttoDouble is VeryHigh

SetEconInvesttoDouble is VeryLow

SetEconInvesttoFull is VeryHigh

SetEconInvesttoFull is VeryLow


Logistics is LVeryHigh

Logistics is LHigh

Logistics is LMedium

Logistics is LLow

Logistics is LVeryLow


DoQuestTask is VeryHigh

DoQuestTask is High

DoQuestTask is Medium

DoQuestTask is Low

DoQuestTask is VeryLow

---









# Per MoveTask Rules


IF MyUnitHP is HPHigh THEN MoveUnittoSpot is High

IF MyUnit HP is HPLow THEN MoveUnittoSpot is VeryLow

IF EnemyUnitHP is HPHigh THEN MoveUnittoSpot is Medium

IF EnemyUnitHP is HPLow THEN MoveUnittoSpot is Low

IF EnemyCityHP is HPHigh THEN MoveUnittoSpot is High

IF EnemyCityHP is HPHigh THEN MoveUnittoSpot is VeryHigh

IF SpotDamage is DamageHigh THEN MoveUnittoSpot is VeryLow

IF SpotDeal is DealHigh THEN MoveUnittoSpot is High

IF SpotEnemDist is DistEnemLow AND MyUnit is FightingUnit AND MyUnitHP is HPHigh THEN MoveUnittoSpot is High

IF SpotEnemDist is DistEnemHigh AND MyUnit is FightingUnit AND MyUnitHP is HPLow THEN MoveUnittoSpot is High

IF SpotMyCityDist is DistMyCityLow AND MyUnit is FightingUnit AND MyUnitHP is HPLow THEN MoveUnittoSpot is High


IF SpotEnemDist is DistEnemHigh AND MyUnit is Pioneer THEN MoveUnittoSpot is High

IF SpotEnemDist is DistEnemLow AND MyUnit is Pioneer THEN MoveUnittoSpot is Low

IF SpotMyCityDist is DistMyCityHigh AND MyUnit is Pioneer THEN MoveUnittoSpot is High

IF SpotMyCityDist is DistMyCityLow AND MyUnit is Pioneer THEN MoveUnittoSpot is Low

# Per AttackTask Rules

IF MyUnitHP is HPHigh THEN AttackUnit is High

IF MyUnit HP is HPLow THEN AttackUnit is VeryLow

IF EnemyUnitHP is HPHigh THEN AttackUnit is Medium

IF EnemyUnitHP is HPLow THEN AttackUnit is Low

IF EnemyCityHP is HPHigh THEN AttackUnit is High

IF EnemyCityHP is HPHigh THEN AttackUnit is VeryHigh

# Per DeployTask Rules

IF SpotEnemDist is DistEnemLow AND MyUnit is FightingUnit THEN DeployUnittoCity is VeryHigh

IF RemainingGold is RemainGoldLow THEN DeployUnittoCity is Low

IF SpotEnemDist is DistEnemHigh AND MyUnit is Pioneer THEN DeployUnittoCity is VeryHigh


IF SpotEnemDist is DistEnemHigh THEN DeployInteriorBuildingtoSpot is VeryHigh

IF CityatSpotRsrcBuildingNum is RsrcBuildingNumHigh THEN DeployInteriorBuildingtoSpot is Low

IF SpotEnemDist is DistEnemLow THEN DeployInteriorBuildingtoSpot is VeryLow

IF CityatSpotRsrcBuildingNum is RsrcBuildingNumLow THEN DeployInteriorBuildingtoSpot is High


IF SpotEnemDist is DistEnemHigh THEN DeployTileResourceBuildingtoSpot is VeryHigh

IF SpotEnemDist is DistEnemLow THEN DeployTileResourceBuildingtoSpot is VeryLow

IF SpotRsrcBuildingNear is SpotRsrcBuildingNearHigh THEN DeployTileResourceBuildingtoSpot is Low

IF SpotRsrcBuildingNear is SpotRsrcBuildingNearLow THEN DeployTileResourceBuildingtoSpot is High


IF SpotMyUnitDist is MyUnitDistLow THEN DeployMilitaryBuildingtoSpot is High

IF SpotEnemDist is DistEnemLow THEN DeployMilitaryBuildingtoSpot is Low


IF NeedCity is High THEN DeployCitytoPioneer is High

IF NeedCity is Medium THEN DeployCitytoPioneer is High

IF NeedCity is Low THEN DeployCitytoPioneer is Medium


# Per UseSkillTask Rules

IF SkillEffect is DamageEnemy AND SkillTargetHP is HPLow AND SkillTarget is Enemy THEN UseSkill is VeryHigh

IF SkillEffect is RestoreAP THEN UseSkill is MostHigh

IF SkillEffect is RestoreHP AND SkillTargetHP is HPLow THEN UseSkill is VeryHigh

IF SkillEffect is RestoreHP AND SkillTargetHP is HPHigh THEN UseSkill is Medium

IF SkillEffect is RestoreHP AND SkillTargetSpot is DamageHigh THEN UseSkill is High

IF SkillEffect is Buff AND SkillTargetSpot is DamageHigh THEN UseSkill is High

IF SkillEffect is Buff AND SkillTargetSpot is DealHigh THEN UseSkill is High

# Per Quest(Pending) Rules


IF QuestReward is UltimateWeaponRsrc THEN AcceptQuest is VeryHigh

IF QuestReward is MilitarySpecRsrc THEN AcceptQuest is High

IF QuestDisplay is DisplayPeriodLow THEN AcceptQuest is Medium

IF QuestDue is DueLow THEN AcceptQuest is High

IF QuestReward is Gold/Labor/Happy/Tech AND [Resource] is [Resource]Low THEN AcceptQuest is High

IF QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff AND [Resource] is [Resource]Low THEN AcceptQuest is High


# Per Quest(Accepted) Rules

IF QuestReward is UltimateWeaponRsrc THEN DoQuestTask is VeryHigh

If QuestReward is MilitarySpecRsrc THEN DoQuestTask is High

If QuestLimit is LimitPeriodLow THEN DoQuestTask is VeryHigh

QuestLimitDue is DueLow THEN DoQuestTask is VeryHigh

QuestReward is Gold/Labor/Happy/Tech THEN DoQuestTask is Medium

QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff THEN DoQuestTask is Medium

# Per Building Rules


IF BuildingProdResource is Gold AND Gold is GoldVeryLow THEN BuildResourceBuilding is VeryHigh

IF BuildingProdResource is Gold AND Gold is GoldLow THEN BuildResourceBuilding is High

IF BuildingProdResource is Gold AND Gold is GoldMedium THEN BuildResourceBuilding is Medium

.

.

.

IF BuildingProdResource is Tech AND Tech is TechVeryHigh THEN BuildResourceBuilding is VeryLow
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MzUwMzMzMzEsMzAxNDQyMjYyXX0=
-->