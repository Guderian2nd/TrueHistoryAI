# IF

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











# THEN

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

DeployTileMilitaryBuildingtoSpot is VeryHigh

DeployTileMilitaryBuildingtoSpot is High

DeployTileMilitaryBuildingtoSpot is Medium

DeployTileMilitaryBuildingtoSpot is Low

DeployTileMilitaryBuildingtoSpot is VeryLow

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

SetHappinessGoal is VeryHigh

SetHappinessGoal is High

SetHappinessGoal is Medium

SetHappinessGoal is Low

SetHappinessGoal is VeryLow

SetEconInvesttoDouble is VeryHigh

SetEconInvesttoDouble is VeryLow

SetEconInvesttoFull is VeryHigh

SetEconInvesttoFull is VeryLow

SetLogisticstoX is VeryHigh

SetLogisticstoX is High

SetLogisticstoX is Medium

SetLogisticstoX is Low

SetLogisticstoX is VeryLow

DoQuestTask is VeryHigh

DoQuestTask is High

DoQuestTask is Medium

DoQuestTask is Low

DoQuestTask is VeryLow

---

# IF THEN

IF MyUnitHP is HPHigh THEN AttackUnit is High
IF MyUnit HP is HPLow THEN AttackUnit is VeryLow
IF EnemyUnitHP is HPHigh THEN AttackUnit is Medium
IF EnemyUnitHP is HPLow THEN AttackUnit is Low
IF EnemyCityHP is HPHigh THEN AttackUnit is High
IF EnemyCityHP is HPHigh THEN AttackUnit is VeryHigh


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


IF SkillEffect is DamageEnemy AND SkillTargetHP is HPLow AND SkillTarget is Enemy THEN UseSkill is VeryHigh
IF SkillEffect is RestoreAP THEN UseSkill is MostHigh
IF SkillEffect is RestoreHP AND SkillTargetHP is HPLow THEN UseSkill is VeryHigh
IF SkillEffect is RestoreHP AND SkillTargetHP is HPHigh THEN UseSkill is Medium
IF SkillEffect is RestoreHP AND SkillTargetSpot is DamageHigh THEN UseSkill is High
IF SkillEffect is Buff AND SkillTargetSpot is DamageHigh THEN UseSkill is High
IF SkillEffect is Buff AND SkillTargetSpot is DealHigh THEN UseSkill is High
IF DeltaFightingUnitNum is DeltaUnitHigh THEN NeedFightingUnit is Low
IF DeltaFightingUnitNum is DeltaUnitMedium THEN NeedFightingUnit is Medium
IF DeltaFightingUnitNum is DeltaUnitLow THEN NeedFightingUnit is High
IF RemainingGold is RemainGoldLow THEN NeedFightingUnit is VeryLow
IF RemainingLabor is RemainLaborLow THEN NeedFightingUnit is VeryLow
IF NeedFightingUnit is High THEN BuildFightingUnit is High
IF NeedFightingUnit is Medium THEN BuildFightingUnit is Medium
IF NeedFightingUnit is Low THEN BuildFightingUnit is Low
IF NeedFightingUnit is VeryLow THEN BuildFightingUnit is VeryLow

IF DeltaCityNum is High THEN NeedCity is Low
IF DeltaCityNum is Low THEN NeedCity is High
IF NeedCity is Low THEN NeedPioneer is VeryLow
IF NeedCity is High THEN NeedPioneer is VeryHigh
IF RemainingGold is RemainGoldLow THEN NeedPioneer is VeryLow
IF RemainingLabor is RemainLaborLow THEN NeedPioneer is VeryLow

IF BuildingProdResource is Gold AND Gold is GoldVeryLow THEN BuildResourceBuilding is VeryHigh
IF BuildingProdResource is Gold AND Gold is GoldLow THEN BuildResourceBuilding is High
IF BuildingProdResource is Gold AND Gold is GoldMedium THEN BuildResourceBuilding is Medium
.
.
.
IF BuildingProdResource is Tech AND Tech is TechVeryHigh THEN BuildResourceBuilding is VeryLow

IF EnemyFightingUnitNum is
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExODU3MDExMTZdfQ==
-->