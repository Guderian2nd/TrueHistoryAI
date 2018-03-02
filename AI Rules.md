[[_TOC_]]



# Global Rules (Common AI)

IF RemainingGold is RemainGoldVeryLow OR RemainingGold is RemainGoldLow THEN NeedFightingUnit is Low

IF RemainingGold is RemainGoldMedium THEN NeedFightingUnit is Medium

IF RemainingGold is RemainGoldHigh OR RemainingGold is RemainGoldVeryHigh THEN NeedFightingUnit is High

IF RemainingLabor is RemainLaborVeryLow OR RemainingLabor is RemainLaborLow THEN NeedFightingUnit is Low

IF RemainingLabor is RemainLaborMedium THEN NeedFightingUnit is Medium

IF RemainingLabor is RemainLaborHigh OR RemainingLabor is RemainLaborVeryHigh THEN NeedFightingUnit is High

IF NeedCity is Low THEN NeedPioneer is VeryLow

IF NeedCity is High THEN NeedPioneer is VeryHigh

IF RemainingGold is RemainGoldVeryLow OR RemainingGold is RemainGoldLow THEN NeedPioneer is Low

IF RemainingGold is RemainGoldMedium THEN NeedPioneer is Medium

IF RemainingGold is RemainGoldHigh OR RemainingGold is RemainGoldVeryHigh THEN NeedPioneer is High

IF RemainingLabor is RemainLaborVeryLow OR RemainingLabor is RemainLaborLow THEN NeedPioneer is Low

IF RemainingLabor is RemainLaborMedium THEN NeedPioneer is Medium

IF RemainingLabor is RemainLaborHigh OR RemainingLabor is RemainLaborVeryHigh THEN NeedPioneer is High

IF AllMyUnitEnemDist is EnemDistLow THEN NeedMilitaryBuilding is High

IF AllMyUnitEnemDist is EnemDistHigh THEN NeedMilitaryBuilding is Low

IF RemainingGold is RemainGoldVeryLow OR RemainingGold is RemainGoldLow THEN NeedMilitaryBuilding is Low

IF RemainingGold is RemainGoldMedium THEN NeedMilitaryBuilding is Medium

IF RemainingGold is RemainGoldHigh OR RemainingGold is RemainGoldVeryHigh THEN NeedMilitaryBuilding is High

IF RemainingLabor is RemainLaborVeryLow OR RemainingLabor is RemainLaborLow THEN NeedMilitaryBuilding is Low

IF RemainingLabor is RemainLaborMedium THEN NeedMilitaryBuilding is Medium

IF RemainingLabor is RemainLaborHigh OR RemainingLabor is RemainLaborVeryHigh THEN NeedMilitaryBuilding is High

IF DeltaHappyGoal is DeltaHappyGoalHigh THEN SetEconInvesttoFull is VeryHigh

IF DeltaHappyGoal is DeltaHappyGoalHigh THEN SetEconInvesttoDouble is VeryLow

IF DeltaHappyGoal is DeltaHappyGoalLow THEN SetEconInvesttoDouble is VeryHigh

IF DeltaHappyGoal is DeltaHappyGoalLow THEN SetEconInvesttoFull is VeryLow

IF RemainingGold is RemainGoldVeryLow OR RemainingGold is RemainGoldLow THEN NeedGold is VeryHigh

IF RemainingGold is RemainGoldVeryHigh OR RemainingGold is RemainGoldHigh THEN NeedGold is VeryLow

IF RemainingGold is RemainGoldMedium THEN NeedGold is Medium

IF RemainingLabor is RemainLaborVeryLow OR RemainingLabor is RemainLaborLow THEN NeedLabor is VeryHigh

IF RemainingLabor is RemainLaborVeryHigh OR RemainingLabor is RemainLaborHigh THEN NeedLabor is VeryLow

IF RemainingLabor is RemainLaborMedium THEN NeedLabor is Medium

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

### Input

RemainingGold: 턴당 금 생산량의 여유로운 정도
* (-infinity, +infinity)
* Def. 현재 남아있는 턴당 금(즉 사용되지 않고 있는)
* RemainGoldSet

RemainingLabor: 턴당 노동력의 여유로운 정도
* [0, +infinity)
* Def. 현재 남아있는 턴당 노동력(즉 사용되지 않고 있는)
* RemainLaborSet

AllMyUnitEnemDist: 얼마나 적 군대와 내 군대가 가까운지의 정도
 * [0, +infinity)
* Def. 각 개별적 내 전투유닛&도시들과 가장 가까운 적 전투유닛과의 거리의 평균, 만약 도시와 유닛이 내가 없을경우 맵의 너비와 높이의 합.
* EnemDistSet

DeltaHappyGoal: 내 목표행복도(Happiness Goal)와 현재 행복도와의 차이 정도
* [-200, +200]
* Def. HappinessGoal(100) - Happy
* DeltaHappySet

Gold: 현재 금 보유량
* [0, +infinity)
* Def. 현재 금 보유량
* GoldSet

Tech: 현재 기술력 보유량
* ibid.
* TechSet

Labor: 현재 노동력 보유량
* ibid.
* LaborSet

Happy: 현재 행복도
* [-100,+100]
* Def. 현재 행복도
* HappySet

TechLost: 기술력이 정복등으로 사라진량
* [0,+infinity)
* Def. 바로전 적국 Subturn때 내가 정복등으로 잃어버린 기술력의 량

TechInvest: 기술계 투자량
* [0,2]
* Def. 기술계 투자량

DmgUnitNum: 피해를 입은 유닛의 전체 유닛중 비율
* [0, 1]
* Def. 피해를 입은 유닛의 갯수/총 유닛의 갯수

Logistics: 병참 투자율
* [0,1]
* Def. 병참 투자율

### Output

NeedFightingUnit: 전투유닛이 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet

NeedCity: 도시가 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet

NeedPioneer: 개척자가 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet

NeedGold: 금이 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSets

NeedLabor: 노동력이 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSets

NeedTech: 기술력이 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSets

NeedLogistics: 병참이 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSets

SetEconInvesttoFull: 민간계투자량을 100%로 하고싶은 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet

SetEconInvesttoDouble: 민간계투자량을 200%로 하고싶은 정도
 * (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet

## Sets

### RemainGold

RemainGoldVeryHigh: [500,1000,+infinity]

RemainGoldHigh: [0, 250,1000,1500]

RemainGoldMedium: [-750,-500,250,750]

RemainGoldLow: [-1500,-1000,-500,0]

RemainGoldVeryLow: [-infinity,-1000,-500]

### RemainLabor

RemainLaborVeryHigh: [500,1000,+infinity]

RemainLaborHigh: [250, 500,750,1000]

RemainLaborMedium: [50,100,250,500]

RemainLaborLow: [15,50,50,100]

RemainLaborVeryLow: [-infinity,25,50]

### EnemDist

EnemDistLow: [-infinity, 3,5]

EnemDistHigh: [4,6,+infinity]

### DeltaHappyGoal

DeltaHappyGoalHigh: <0,0,200>

DeltaHappyGoalLow: <-200,0,0>

### TechLost

TechLostHigh: [2500,5000,+infinity]

TechLostMedium: [0,2500,5000,7500]

TechLostLow: [-infinity,2500,5000]

### Gold

GoldHigh: [2500, 5000, +infinity]

GoldNormal: [0,2500,5000,7500]

GoldLow: [-infinity,2500,5000]

### Tech

TechHigh: [10000,20000,+infinity]

TechNormal: [5000,10000,20000,25000]

TechLow: [-infinity,5000,10000]

### Labor

LaborHigh: [1000,2000,+infinity]

LaborNormal: [250,500,1000,1500]

LaborLow: [0,100,250,500]

### Happy

HappyHigh: [50,75,100,100]

HappyNormal: [0,25,50,75]

HappyLow: [-100,-100,0,25]

### T

THigh: [1,1.5,2,2]

TMedium: [0.5,0.75,1.25,1.5]

TLow: [-infinity,0.5,1]

### UnitNum

UnitNumHigh: [0.5,0.75,1,1]

UnitNumMedium: [0.2,0.4,0.6,0.8]

UnitNumLow: [0,0.1,0.2,0.25]

UnitNumVeryLow: [-infinity, 0.1, 0.15]

### L

LHigh: [0.7, 0.9, infinity]

LMedium: [0.5,0.7,0.9]

LLow: [0.4,0.5,0.6]

LVeryLow: [-infinity, 0.4, 0.5]

# Global Additional Rules(Suomi/Hwan)

IF DeltaCityNum is CityHigh THEN NeedCity is Low

IF DeltaCityNum is CityMedium THEN NeedCity is Medium

IF DeltaCityNum is CityLow THEN NeedCity is High

IF DeltaFightingUnitNum is DeltaUnitHigh THEN NeedFightingUnit is Low

IF DeltaFightingUnitNum is DeltaUnitMedium THEN NeedFightingUnit is Medium

IF DeltaFightingUnitNum is DeltaUnitLow THEN NeedFightingUnit is High

IF EnemyFightingUnitNum is FightingUnitNumHigh THEN NeedMilitaryBuilding is High

IF EnemyFightingUnitNum is FightingUnitNumMedium THEN NeedMilitaryBuilding is Medium

IF EnemyFightingUnitNum is FightingUnitNumLow THEN NeedMilitaryBuilding is Low


## Variables
### Input
DeltaFightingUnitNum : 적의 유닛 갯수 & 도시 갯수 와 내 현재 유닛 + 생산되고 있는 갯수와의 차이
* (-infinity,+infinity)
* Def. (My Fighting Unit Number + My Fighting Unit Being Produced Number) - (1.5 × Enemy Fighting Unit Number + Enemy City Number)
* DeltaUnitSets

DeltaCityNum: 적 도시 갯수와 내 잠재적 도시 갯수와의 차이
* (-infinity, +infinity)
* Def. (My City Number + My Pioneer Number + Max(My Pioneer Under Production Number, My City Center Under Production)) - (1.5 × Enemy City Number)
* CityNumSet

EnemFightingUnitNum: 적 전투유닛의 갯수
* [0, +infinity)
* Def. 적 전투유닛의 갯수
* FightingUnitNumSet



## Sets

### DeltaUnit

DeltaUnitHigh: [0, 0,50,+infinity]

DeltaUnitMedium: [-70, -50, 50, 70]

DeltaUnitLow: [-infinity, -50, 0]

### CityNum

CityHigh: [+10,+20,+infinity]

CityMedium: [-20,-10,+10,+20]

CityLow: [-infinity,-20,-10]

### FightingUnitNum

FightingUnitNumHigh: [25,50,+infinity]

FightingUnitNumMedium:[0,25,50,75]

FightingUnitNumLow:[-infinity,0,25]

# Global Additional Rules(Other)

IF MyFightingUnitNum is FightingUnitNumHigh THEN NeedFightingUnit is VeryLow

IF MyFightingUnitNum is FightingUnitNumMedium THEN NeedFightingUnit is Low

IF MyFightingUnitNum is FightingUnitNumLow THEN NeedFightingUnit is High

IF MyCityNum is MyCityNumHigh THEN NeedCity is VeryLow

IF MyCityNum is MyCityNumMedium THEN NeedCity is Low

IF MyCityNum is MyCityNumLow THEN NeedCity is High

## Variables

### Input

MyFightingUnitNum: 내가 가지고 있는 총 전투 유닛의 갯수 + 생산되고 있는 전투 유닛의 갯수
* [0,+infinity)
* Def. My Fighting Unit Number + My Fighting Unit Under Production
* FightingUnitNumSet

MyCityNum: 내가 가지고 있는 총 도시의 갯수 + 잠재적 도시 갯수
* [0, +infinity)
* Def. (My City Number + My Pioneer Number + Max(My Pioneer Under Production Number, My City Center Under Production))
* MyCityNumSet


### Output
NeedCity: 도시가 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet

NeedPioneer: 개척자가 필요한 정도
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet


## Sets

### FightingUnitNum

FightingUnitNumHigh: [25,50,+infinity]

FightingUnitNumMedium:[0,25,50,75]

FightingUnitNumLow:[-infinity,0,25]


### MyCityNum

MyCityNumHigh: [4,6,+infinity)

MyCityNumMedium: [2,4,6,8]

MyCityNumLow: (-infinity, 2,4]

# Per MoveTask Rules(Common)


IF MyUnitHP is HPHigh THEN MoveUnittoSpot is High

IF MyUnitHP is HPLow THEN MoveUnittoSpot is VeryLow

IF EnemyUnitHP is HPHigh THEN MoveUnittoSpot is Medium

IF EnemyUnitHP is HPLow THEN MoveUnittoSpot is Low

IF EnemyCityHP is HPHigh THEN MoveUnittoSpot is High

IF EnemyCityHP is HPHigh THEN MoveUnittoSpot is VeryHigh

IF SpotDamage is DamageHigh THEN MoveUnittoSpot is VeryLow

IF SpotDamage is DamageMedium THEN MoveUnittoSpot is Low

IF SpotDamage is DamageLow THEN MoveUnittoSpot is Medium

IF SpotDeal is DealHigh THEN MoveUnittoSpot is High

IF SpotDeal is DealLow THEN MoveUnittoSpot is Low

IF SpotEnemDist is DistEnemMedium THEN MoveUnittoSpot is Low

IF SpotMyCityDist is DistMyCityMedium THEN MoveUnittoSpot is Low

IF SpotEnemDist is DistEnemLow AND MyUnit is FightingUnit AND MyUnitHP is HPHigh THEN MoveUnittoSpot is High

IF SpotEnemDist is DistEnemHigh AND MyUnit is FightingUnit AND MyUnitHP is HPLow THEN MoveUnittoSpot is High

IF SpotMyCityDist is DistMyCityLow AND MyUnit is FightingUnit AND MyUnitHP is HPLow THEN MoveUnittoSpot is High


IF SpotEnemDist is DistEnemHigh AND MyUnit is Pioneer THEN MoveUnittoSpot is High

IF SpotEnemDist is DistEnemLow AND MyUnit is Pioneer THEN MoveUnittoSpot is Low

IF SpotMyCityDist is DistMyCityHigh AND MyUnit is Pioneer THEN MoveUnittoSpot is High

IF SpotMyCityDist is DistMyCityLow AND MyUnit is Pioneer THEN MoveUnittoSpot is Low

## Variables
### Input
MyUnit : 해당 Task의 주체가 되는 유닛의 종류
* [0,1]
* Def. [FightingUnit, Pioneer] - 전투유닛 아니면 개척자, 둘중 하나
* UnitTypeSet

MyUnitHP: 해당 Task의 주체가 만약 이 Task를 시행했을시의 결과로 나오는, 해당 유닛의 HP가 풀피에서 남아있는 비율
* [0,1]
* Def. (해당 Task를 실행후 남아있는 유닛의 실제 HP)/(유닛의 풀HP)
* HPSet

EnemyUnitHP: 만약 해당 MoveTask가 Moving Attack이며 공격대상이 일반적 유닛일때, 공격받는 적 유닛의 Task시행후 남아있는 HP의 비율
* [0,1]
* Def. (해당 Task를 실행후 남아있는 공격받은 적 유닛의 실제 HP)/(유닛의 풀HP)
* HPSet

EnemyCityHP: 만약 해당 MoveTask가 Moving Attack이며 공격대상이 도시일때, 공격받는 도시의 Task시행후 남아있는 HP의 비율
* [0,1]
* Def. (해당 Task를 실행후 남아있는 공격받은 도시의 실제 HP)/(도시의 풀HP)
* HPSet

SpotDamage: 현재 타일에서 적 유닛들에게서 받을수 있는 총 데미지량(최대 HP의 비율로 나타낸)과 해당 MoveTask가 이동하고자 하는 타일에서 적 유닛들에게서 받을수 있는 총 데미지량(스킬 제외, 이동공격포함) 의 차
* (-infinity,+infinity)
* Def. Σ (목표 타일을 다음 서브턴에 공격할수 있는 적 유닛의 공격력)/(MovingTask주체 유닛의 최대 HP) -  Σ (현재 타일을 다음 서브턴에 공격할수 있는 적 유닛의 공격력)/(MovingTask주체 유닛의 최대 HP) 
* DamageSet

SpotDeal: 현재 타일에서 다음 서브턴에 공격할수 있는 적 유닛들의 갯수와 해당 MoveTask가 이동하고자하는 타일에서 다음 서브턴에 공격할수 있는 적 유닛들의 갯수(스킬 제외, 이동공격포함)의 차
*  (-infinity,+infinity)
* Def. (목표 타일에 근접해 있거나 이동공격할수 있는 유닛의 갯수) -  (현재 타일에 근접해 있거나 이동공격할수 있는 유닛의 갯수)
* DealSet

SpotEnemDist: 현재 타일에서 제일 가까운 적 유닛/도시까지의 거리와 해당 MoveTask가 이동하고자 하는 타일에서 제일 가까운 적 유닛/도시까지의 거리의 차
*  (-infinity,+infinity)
* Def. (목표 타일에 제일 가까운 적 유닛/도시까지의 거리) - (현재 타일에 제일 가까운 적 유닛/도시까지의 거리)
* DistEnemSet

SpotMyCityDist: 현재 타일에서 제일 가까운 내 도시까지의 거리와 해당 MoveTask가 이동하고자 하는 타일에서 제일 가까운 내 도시까지의 거리의 차
*  (-infinity,+infinity)
* Def. (목표 타일에 제일 가까운 내 도시까지의 거리) - (현재 타일에 제일 가까운 내 도시까지의 거리)
* DistMyCitySet

### Output

MoveUnittoSpot: 한 유닛을 한 특정한 장소로 이동시키는 Task의 점수
* (-1,+1)
* Def. [VeryLow, Low, Medium, Low, High]
* ResultSet


## Sets

### UnitType
FightingUnit: <0>

Pioneer: <1>

### HP
HPHigh: [0.5, 0.75, +infinity]

HPLow: [-infinity, 0.3, 0.6]

### Damage
DamageHigh: [0.3,0.6,+infinity]

DamageMedium: [-0.4,-0.2,0.2,0.4]

DamageLow:  [-infinity, -0.6, -0.3]

### Deal
DealHigh: [0,1,+infinity]

DealMedium: [-1,0,1]

DealLow: [-infinity, -1,0]
### DistEnem

DistEnemHigh: [0,0.5,+infinity]

DistEnemMedium: [-0.5,0,0.5]

DistEnemLow: [-infinity,-0.5,0]

### DistMyCity

DistMyCityHigh: [0,0.5,+infinity]

DistMyCityMedium: [-0.5,0,0.5]

DistMyCityLow: [-infinity,-0.5,0]

# Per MoveTask Rules(Other)

IF SpotOwner is Enemy OR SpotOwner is Ally THEN MoveUnittoSpot is VeryLow

IF SpotOwner is Me THEN MoveUnittoSpot is Medium

## Variables
### Input
SpotOwner: 해당 MoveTask로 이동하고자 하는 타일의 주인
* [0,1,2]
* Def. [Me, Enemy, Ally] - Ally는 동맹이지만 내가 아닌 타일 주인 국가
* OwnerType


## Sets

### OwnerType

Me: <0>
Enemy: <1>
Ally: <2>

# Per AttackTask Rules

IF MyUnitHP is HPHigh THEN AttackUnit is High

IF MyUnit HP is HPLow THEN AttackUnit is VeryLow

IF EnemyUnitHP is HPHigh THEN AttackUnit is Medium

IF EnemyUnitHP is HPLow THEN AttackUnit is Low

IF EnemyCityHP is HPHigh THEN AttackUnit is High

IF EnemyCityHP is HPHigh THEN AttackUnit is VeryHigh

## Variables

## Sets

# Per DeployTask Rules

IF DeploySpotEnemDist is DeployDistEnemLow AND MyUnit is FightingUnit THEN DeployUnittoCity is VeryHigh

IF RemainingGold is RemainGoldLow THEN DeployUnittoCity is Low

IF DeploySpotEnemDist is DeployDistEnemHigh AND MyUnit is Pioneer THEN DeployUnittoCity is VeryHigh


IF DeploySpotEnemDist is DeployDistEnemHigh THEN DeployInteriorBuildingtoSpot is VeryHigh

IF CityatSpotRsrcBuildingNum is RsrcBuildingNumHigh THEN DeployInteriorBuildingtoSpot is Low

IF DeploySpotEnemDist is DistEnemLow THEN DeployInteriorBuildingtoSpot is VeryLow

IF CityatSpotRsrcBuildingNum is RsrcBuildingNumLow THEN DeployInteriorBuildingtoSpot is High


IF DeploySpotEnemDist is DeployDistEnemHigh THEN DeployTileResourceBuildingtoSpot is VeryHigh

IF DeploySpotEnemDist is DeployDistEnemLow THEN DeployTileResourceBuildingtoSpot is VeryLow

IF SpotRsrcBuildingNear is SpotRsrcBuildingNearHigh THEN DeployTileResourceBuildingtoSpot is Low

IF SpotRsrcBuildingNear is SpotRsrcBuildingNearLow THEN DeployTileResourceBuildingtoSpot is High


IF SpotMyUnitDist is MyUnitDistLow THEN DeployMilitaryBuildingtoSpot is High

IF DeploySpotEnemDist is DeployDistEnemLow THEN DeployMilitaryBuildingtoSpot is Low


IF NeedCity is High THEN DeployCitytoPioneer is High

IF NeedCity is Medium THEN DeployCitytoPioneer is High

IF NeedCity is Low THEN DeployCitytoPioneer is Medium

## Variables

CityatSpotRsrcBuildingNum: 해당 Deploy Task가 Deploy하려는 위치(도시)에 존재하는 동일 종류의 자원 건물의 갯수
* [0,infinity)
* Def. 해당 Deploy Task가 Deploy하려는 위치(도시)에 존재하는 동일 종류의 자원 건물의 갯수

SpotRsrcBuildingNear : 해당 Deploy Task가 Deploy하려는 타일 주변에 존재하는 자원건물의 갯수
* [0,infinity)
* Def. 해당 Deploy Task가 Deploy하려는 타일 3칸 이내에 존재하는 자원 타일 건물들의 갯수

SpotMyUnitDist: 해당 Deploy Task가 Deploy하려는 타일로부터 제일 가까운 아군 유닛까지의 거리
* [0,infinity)
* 해당 Deploy Task가 Deploy하려는 타일로부터 제일 가까운 아군 유닛까지의 거리

DeploySpotEnemDist: 해당 Deploy Task가 Deploy하려는 타일로부터 제일 가까운 적 유닛까지의 거리
* [0,infinity)
* 해당 Deploy Task가 Deploy하려는 타일로부터 제일 가까운 적 유닛까지의 거리

DeployUnittoCity:
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

DeployInteriorBuildingtoSpot:
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

DeployTileResourceBuildingtoSpot:
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

DeployMilitaryBuildingtoSpot: 
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

DeployCitytoPioneer:
* (-infinity,+infinity)
* Def. [VeryLow, Low, Medium, Low, High]

## Sets

RsrcBuildingNumHigh: [40,80,+infinity)

RsrcBuildingNumLow: [-infinity,40,80]

SpotRsrcBuildingNearHigh: [12,24,36,36>

SpotRsrcBuildingNearLow: <0,0,12,24]

MyUnitDistHigh: [5,8,+infinity]

MyUnitDistLow: <0,0,3,6]

DeployDistEnemHigh: [5,8,+infinity]

DeployDistEnemLow: <0,0,3,6]


# Per UseSkillTask Rules

IF SkillEffect is DamageEnemy AND SkillTargetHP is HPLow AND SkillTarget is Enemy THEN UseSkill is VeryHigh

IF SkillEffect is DamageEnemy AND SkillTargetHP is HPHigh AND SkillTarget is Enemy THEN UseSkill is High

IF SkillEffect is RestoreAP THEN UseSkill is MostHigh

IF SkillEffect is RestoreHP AND SkillTargetHP is HPLow AND SkillTarget is Ally THEN UseSkill is VeryHigh

IF SkillEffect is RestoreHP AND SkillTargetHP is HPHigh  AND SkillTarget is Ally THEN UseSkill is Medium

IF SkillEffect is RestoreHP AND SkillTargetSpotDamage is SpotDamageHigh AND SkillTarget is Ally THEN UseSkill is High

IF SkillEffect is Buff AND SkillTargetSpotDamage is SpotDamageHigh AND SkillTarget is Ally THEN UseSkill is High

IF SkillEffect is Buff AND SkillTargetSpotDeal is SpotDealHigh AND SkillTarget is Ally THEN UseSkill is High

## Variables

SkillEffect: 해당 UseSkillTask의 주체가 사용하고자 하는 스킬의 효과
* [0, 1,2,3]
* Def.  [DamageEnemy, RestoreAP, RestoreHP, Buff]

SkillTarget: 해당 UseSkillTask의 주체가 사용하고자 하는 스킬의 대상이 적군인지 아군인지(대상이 있는 스킬이면)
* [0,1]
* Def. [Ally, Enemy]

SkillTargetHP: 해당 UseSkillTask의 주체가 사용하고자 하는 스킬의 대상의 HP가 풀피에서 남아있는 비율
* [0,1]
* Def. (해당 UseSkillTask의 주체가 사용하고자 하는 스킬의 대상의 현재 HP)/(대상의 풀HP)

SkillTargetSpotDamage: 해당 UseSkillTask의 주체가 사용하고자 하는 스킬의 대상의 위치에서 받을수 있는 총 데미지량(풀피의 비율로 나타낸)의 합
* [0,+infinity)
* Def. Σ (UseSkillTask의 대상 유닛 타일을 다음 서브턴에 공격할수 있는 적 유닛의 공격력)/(UseSkillTask의 대상 유닛의 최대 HP)

SkillTargetSpotDeal: 해당 UseSkillTask의 주체가 사용하고자 하는 스킬의 대상의 위치에서 공격할수 있는 총 적 유닛의 갯수
* [0,+infinity)
* (목표 타일에 근접해 있거나 이동공격할수 있는 유닛의 갯수)



## Sets

DamageEnemy: <0>

RestoreAP: <1>

RestoreHP: <2>

Buff: <3>

Ally: <0>

Enemy: <1>





# Per Quest(Pending) Rules


IF QuestReward is UltimateWeaponRsrc THEN AcceptQuest is VeryHigh

IF QuestReward is MilitarySpecRsrc THEN AcceptQuest is High

IF QuestDisplay is DisplayPeriodLow THEN AcceptQuest is Medium

IF QuestDue is DueLow THEN AcceptQuest is High

IF QuestReward is Gold/Labor/Happy/Tech AND [Resource] is [Resource]Low THEN AcceptQuest is High

IF QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff AND [Resource] is [Resource]Low THEN AcceptQuest is High

## Variables

## Sets

# Per Quest(Accepted) Rules

IF QuestReward is UltimateWeaponRsrc THEN DoQuestTask is VeryHigh

If QuestReward is MilitarySpecRsrc THEN DoQuestTask is High

If QuestLimit is LimitPeriodLow THEN DoQuestTask is VeryHigh

QuestLimitDue is DueLow THEN DoQuestTask is VeryHigh

QuestReward is Gold/Labor/Happy/Tech THEN DoQuestTask is Medium

QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff THEN DoQuestTask is Medium

## Variables

## Sets

# Per Building Rules (Common)


IF BuildingProdResource is Gold AND (Gold is GoldLow OR NeedGold is VeryHigh OR NeedGold is High) THEN BuildResourceBuilding is VeryHigh

IF BuildingProdResource is Gold AND (Gold is GoldMedium OR NeedGold is Medium) THEN BuildResourceBuilding is Medium

IF BuildingProdResource is Gold AND (Gold is GoldHigh OR NeedGold is Low OR NeedGold is VeryLow) THEN BuildResourceBuilding is Low

IF BuildingProdResource is Tech AND (Tech is TechLow OR NeedTech is VeryHigh OR NeedTech is High) THEN BuildResourceBuilding is VeryHigh

IF BuildingProdResource is Tech AND (Tech is TechMedium OR NeedTech is Medium) THEN BuildResourceBuilding is Medium

IF BuildingProdResource is Tech AND (Tech is TechHigh OR NeedTech is Low OR NeedTech is VeryLow) THEN BuildResourceBuilding is Low


IF BuildingProdResource is Labor AND (Labor is LaborLow OR NeedLabor is High OR NeedLabor is VeryHigh) THEN BuildResourceBuilding is High

IF BuildingProdResource is Labor AND (Labor is LaborMedium OR NeedLabor is Medium) THEN BuildResourceBuilding is Medium

IF BuildingProdResource is Labor AND (Labor is LaborHigh OR NeedLabor is Low OR NeedLabor is VeryLow) THEN BuildResourceBuilding is Low


IF BuildingProdResource is Happy AND (Happy is HappyLow OR NeedHappy is High OR NeedHappy is VeryHigh) THEN BuildResourceBuilding is High

IF BuildingProdResource is Happy AND (Happy is HappyMedium OR NeedHappy is Medium) THEN BuildResourceBuilding is Medium

IF BuildingProdResource is Happy AND (Happy is HappyHigh OR NeedHappy is Low OR NeedHappy is VeryLow) THEN BuildResourceBuilding is Low


## Variables

BuildingProdResource: 해당 BuildTask가 지으려는 건물이 

## Sets


# IF

MyUnitHP is HPHigh

MyUnitHP is HPLow

EnemyUnitHP is HPHigh

EnemyUnitHP is HPLow

EnemyCityHP is HPHigh

EnemyCityHP is HPLow

---

SpotDamage is DamageHigh

SpotDeal is DealHigh

SpotEnemDist is DistEnemHigh

SpotEnemDist is DistEnemLow

SpotMyCityDist is DistMyCityHigh

SpotMyCityDist is DistMyCityLow

---

SkillEffect is DamageEnemy

SkillEffect is RestoreAP

SkillEffect is RestoreHP

SkillEffect is Buff

---

SkillTargetHP is HPHigh

SkillTargetHP is HPLow

SkillTargetSpot is DamageHigh

SkillTargetSpot is DealHigh

---

DeltaFightingUnitNum is DeltaUnitHigh

DeltaFightingUnitNum is DeltaUnitLow

---

NeedFightingUnit is High

NeedFightingUnit is Low

---

DeltaCityNum is DeltaCityHigh

DeltaCityNum is DeltaCityLow

---

RemainingGold is RemainGoldHigh

RemainingGold is RemainGoldLow

RemainingLabor is RemainLaborHigh

RemainingLabor is RemainLaborLow


---
BuildingProdResource is Gold/Labor/Tech/Happy


---
Gold is GoldHigh

Gold is GoldMedium

Gold is GoldLow

마찬가지

EnemyFightingUnitNum is FightingUnitNumHigh


---
AllMyUnitEnemDist is EnemDistHigh ... 

---

MyUnit is FightingUnit

MyUnit is Pioneer

---

CityatSpotRsrcBuildingNum is RsrcBuildingNumHigh

CityatSpotRsrcBuildingNum is RsrcBuildingNumLow


---
SpotRsrcBuildingNear is SpotRsrcBuildingNearHigh

SpotRsrcBuildingNear is SpotRsrcBuildingNearLow

---

SpotMyUnitDist is MyUnitDistHigh

SpotMyUnitDist is MyUnitDistLow

---

QuestReward is UltimateWeaponRsrc

QuestReward is MilitarySpecRsrc

QuestDisplay is DisplayPeriodLow

QuestDue is DueLow

QuestReward is Gold/Labor/Happy/Tech

QuestReward is Goldbuff/Laborbuff/Happybuff/Techbuff

---

DeltaHappyGoal is DeltaHappyGoalHigh

DeltaHappyGoal is DeltaHappyGoalLow


---
NeedLabor is High

NeedLabor is Medium

NeedLabor is Low

NeedGold is VeryHigh

NeedGold is High

NeedGold is Medium

NeedGold is Low

---

Tech is TechHigh

Tech is TechMedium

Tech is TechLow


---
NeedTech is High

NeedTech is Medium

NeedTech is Low

---

DmgUnitNum is High

DmgUnitNum is Medium

DmgUnitNum is Low


---
NeedLogistics is High

NeedLogistics is Medium

NeedLogistics is Low



# THEN

AttackUnit is VeryHigh

AttackUnit is High

AttackUnit is Medium

AttackUnit is Low

AttackUnit is VeryLow

---

MoveFightingUnittoSpot is VeryHigh

MoveFightingUnittoSpot is High

MoveFightingUnittoSpot is Medium

MoveFightingUnittoSpot is Low

MoveFightingUnittoSpot is VeryLow

---

MovePioneertoSpot is VeryHigh

MovePioneertoSpot is High

MovePioneertoSpot is Medium

MovePioneertoSpot is Low

MovePioneertoSpot is VeryLow

---

UseSkill is VeryHigh

UseSkill is High

UseSkill is Medium

UseSkill is Low

UseSkill is VeryLow

---



BuildFightingUnit is VeryHigh

BuildFightingUnit is High

BuildFightingUnit is Medium

BuildFightingUnit is Low

BuildFightingUnit is VeryLow

---

BuildResourceBuilding is VeryHigh

BuildResourceBuilding is High

BuildResourceBuilding is Medium

BuildResourceBuilding is Low

BuildResourceBuilding is VeryLow

---

BuildMilitaryBuilding is VeryHigh

BuildMilitaryBuilding is High

BuildMilitaryBuilding is Medium

BuildMilitaryBuilding is Low

BuildMilitaryBuilding is VeryLow

---

DeployUnittoCity is VeryHigh

DeployUnittoCity is High

DeployUnittoCity is Medium

DeployUnittoCity is Low

DeployUnittoCity is VeryLow

---

DeployInteriorBuildingtoCity is VeryHigh

DeployInteriorBuildingtoCity is High

DeployInteriorBuildingtoCity is Medium

DeployInteriorBuildingtoCity is Low

DeployInteriorBuildingtoCity is VeryLow

---

DeployTileResourceBuildingtoSpot is VeryHigh

DeployTileResourceBuildingtoSpot is High

DeployTileResourceBuildingtoSpot is Medium

DeployTileResourceBuildingtoSpot is Low

DeployTileResourceBuildingtoSpot is VeryLow


---
DeployMilitaryBuildingtoSpot is VeryHigh

DeployMilitaryBuildingtoSpot is High

DeployMilitaryBuildingtoSpot is Medium

DeployMilitaryBuildingtoSpot is Low

DeployMilitaryBuildingtoSpot is VeryLow

---

DeployCitytoPioneer is VeryHigh

DeployCitytoPioneer is High

DeployCitytoPioneer is Medium

DeployCitytoPioneer is Low

DeployCitytoPioneer is VeryLow


---
AcceptQuest is VeryHigh

AcceptQuest is High

AcceptQuest is Medium

AcceptQuest is Low

AcceptQuest is VeryLow


---
HappinessGoal is HVeryHigh

HappinessGoal is HHigh

HappinessGoal is HMedium

HappinessGoal is HLow

HappinessGoal is HVeryLow

---

SetEconInvesttoDouble is VeryHigh

SetEconInvesttoDouble is VeryLow

SetEconInvesttoFull is VeryHigh

SetEconInvesttoFull is VeryLow

---

Logistics is LVeryHigh

Logistics is LHigh

Logistics is LMedium

Logistics is LLow

Logistics is LVeryLow

---

DoQuestTask is VeryHigh

DoQuestTask is High

DoQuestTask is Medium

DoQuestTask is Low

DoQuestTask is VeryLow


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2OTUwNzU3NTgsOTcxOTQxOTE2LC0xMj
AxMDE5MTAzLDk3MTk0MTkxNiwtMTIwMTAxOTEwMyw5NzE5NDE5
MTYsLTEyMDEwMTkxMDMsOTcxOTQxOTE2LC01MTAzOTUwMzQsND
UwNTM2MDY4LDE1NTA5NDY1NTQsNTc4NjE3ODQsLTc0MTc3NDE1
LC0xMTUzMDA4MDI2LDMwMTQ0MjI2Ml19
-->