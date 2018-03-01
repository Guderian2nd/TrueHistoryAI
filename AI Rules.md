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

IF DeltaCityNum is CityLow THEN NeedCity is High

IF NeedCity is Low THEN NeedPioneer is VeryLow

IF NeedCity is High THEN NeedPioneer is VeryHigh

IF RemainingGold is RemainGoldLow THEN NeedPioneer is VeryLow

IF RemainingLabor is RemainLaborLow THEN NeedPioneer is VeryLow

If NeedCity is High THEN BuildCityCenter is High

If NeedCity is Low THEN BuildCityCenter is Low

If NeedPioneer is High THEN BuildPioneer is High

If NeedPioneer is Low THEN BuildPioneer is Low


IF BuildingProdResource is Gold AND Gold is GoldVeryLow THEN BuildResourceBuilding is VeryHigh

IF BuildingProdResource is Gold AND Gold is GoldLow THEN BuildResourceBuilding is High

IF BuildingProdResource is Gold AND Gold is GoldMedium THEN BuildResourceBuilding is Medium

.

.

.

IF BuildingProdResource is Tech AND Tech is TechVeryHigh THEN BuildResourceBuilding is VeryLow


IF EnemyFightingUnitNum is FightingUnitNumHigh THEN BuildMilitaryBuilding is High

IF EnemyFightingUnitNum is FightingUnitNumLow THEN BuildMilitaryBuilding is Low

IF AllMyUnitEnemDist is EnemDistLow THEN BuildMilitaryBuilding is High

IF RemainingGold is RemainGoldLow THEN BuildMilitaryBuilding is VeryLow

IF RemainingLabor is RemainLaborLow THEN BuildMilitaryBuilding is VeryLow



IF NeedCity is High THEN DeployCitytoPioneer is High

IF NeedCity is Medium THEN DeployCitytoPioneer is High

IF NeedCity is Low THEN DeployCitytoPioneer is Medium


IF QuestReward is UltimateWeaponRsrc THEN AcceptQuest is VeryHigh

IF QuestReward is MilitarySpecRsrc THEN AcceptQuest is High

IF QuestDisplay is DisplayPeriodLow THEN AcceptQuest is Medium

IF QuestDue is DueLow THEN AcceptQuest is High

IF QuestReward is Gold/Labor/Happy/Tech AND [Resource] is [Resource]Low THEN AcceptQuest is High

IF QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff AND [Resource] is [Resource]Low THEN AcceptQuest is High


IF DeltaHappyGoal is DeltaHappyGoalHigh THEN SetEconInvesttoFull is VeryHigh

IF DeltaHappyGoal is DeltaHappyGoalHigh THEN SetEconInvesttoDouble is VeryLow

IF DeltaHappyGoal is DeltaHappyGoalLow THEN SetEconInvesttoDouble is VeryHigh

IF DeltaHappyGoal is DeltaHappyGoalLow THEN SetEconInvesttoFull is VeryLow


If NeedLabor is High THEN HappinessGoal is HVeryHigh

If NeedGold is VeryHigh THEN HappinessGoal is HLow


IF TechLost is True THEN NeedTech is VeryHigh

IF Tech is TechHigh THEN NeedTech is Low

IF Tech is TechNormal THEN NeedTech is Medium

IF Tech is TechLow THEN NeedTech is High

IF NeedGold is VeryHigh THEN NeedTech is VeryLow

IF NeedTech is High THEN TechInvest is THigh

IF NeedTech is Medium THEN TechInvest is TMedium

IF NeedTech is Low THEN TechInvest is TLow


IF DmgUnitNum is High THEN NeedLogistics is High

IF DmgUnitNum is Medium THEN NeedLogistics is Medium

IF DmgUnitNum is Low THEN NeedLogistics is Low

IF DmgUnitNum is VeryLow THEN NeedLogistics is VeryLow

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
* [0, +infinity)
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

NeedPioneer: 개척자가 필요한 정도

BuildCityCenter: 실제로 도시를 생산할 정도

BuildPioneer: 실제로 개척자를 생산할 정도










## Sets

DeltaUnitHigh: [0,50,+infinity]
DeltaUnitMedium: [-70, -30, 30, 70]
DeltaUnitLow: [-infinity, -50, 0]


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

IF SpotEnemDist is DistEnemLow THEN DeployMilitaryBuildingtoSpot is Low]

# Per UseSkillTask Rules

IF SkillEffect is DamageEnemy AND SkillTargetHP is HPLow AND SkillTarget is Enemy THEN UseSkill is VeryHigh

IF SkillEffect is RestoreAP THEN UseSkill is MostHigh

IF SkillEffect is RestoreHP AND SkillTargetHP is HPLow THEN UseSkill is VeryHigh

IF SkillEffect is RestoreHP AND SkillTargetHP is HPHigh THEN UseSkill is Medium

IF SkillEffect is RestoreHP AND SkillTargetSpot is DamageHigh THEN UseSkill is High

IF SkillEffect is Buff AND SkillTargetSpot is DamageHigh THEN UseSkill is High

IF SkillEffect is Buff AND SkillTargetSpot is DealHigh THEN UseSkill is High

# Per Quest(Pending) Rules

# Per Quest(Accepted) Rules

IF QuestReward is UltimateWeaponRsrc THEN DoQuestTask is VeryHigh

If QuestReward is MilitarySpecRsrc THEN DoQuestTask is High

If QuestLimit is LimitPeriodLow THEN DoQuestTask is VeryHigh

QuestLimitDue is DueLow THEN DoQuestTask is VeryHigh

QuestReward is Gold/Labor/Happy/Tech THEN DoQuestTask is Medium

QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff THEN DoQuestTask is Medium

# Per Building Rules


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIxNDM3Njk0NiwzMDE0NDIyNjJdfQ==
-->