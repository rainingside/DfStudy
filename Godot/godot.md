godot
[toc]

# 游戏架构
## 全局单例

## 信号总线 或 自定义实现发布订阅的MessageServer

## 管理器
- 主管理器
  负责协调各个子管理器
- 子管理器
  每个管理器实现对应的管理器接口，各功能模块添加管理器接口交互

## InputProvider
    玩家、敌人等各个角色都有自己的InputProvider，从对应InputProvider中获取输入

## Components
    每个角色有多个Component构成 各司其职

# 实用技巧
## 有限状态机

## 策略模式

## 简单继承

## HitBox HurtBox 受击框 攻击框

## 组合架构技能、buf系统
- AbilityComponent​ 
    技能系统核心组件 挂载在各个角色上
    持有并管理多个Ability实例
- Ability (技能实例)​
    代表一个具体的技能，不直接实现逻辑，而是作为AbilityEffect的容器
- AbilityEffect (技能效果)​
    核心功能单元，以组件形式实现具体技能逻辑（如伤害、治疗、施加Buff）。
    被Ability持有，在特定时机被触发。
- AbilityCost (技能消耗)​
    负责技能的资源消耗逻辑，如魔法值、体力值。
    在技能释放前由Ability调用检查。
- TargetSelector (目标选择)​
    负责技能的目标选择逻辑，如扇形区域、直线范围、单体目标。
    在技能释放时由AbilityEffect调用。
这个架构通过AbilityComponent作为总控中心，协调各个部分有条不紊地工作
    
