# SixDoF Arm MoveIt! 

このリポジトリは、MoveIt! を使った6自由度マニピュレータの動作デモです。
URDFの自動生成、MoveIt! 設定、RVizによる可視化、基本的な動作コマンドを含みます。

---

## デモの概要

* ROS 2 Humble
* MoveIt 2
* マニピュレータ構成：6自由度
* URDFはCSVから自動生成（[`csv2urdf`](https://github.com/ttakubo/csv2urdf) ベース）

---

## セットアップ手順

```bash
# ワークスペースの作成
mkdir -p ~/moveit_ws/src
cd ~/moveit_ws/src
git clone https://github.com/kyosuke423/moveit_ws.git
cd ..
colcon build
source install/setup.bash
```

---

## URDF生成（必要な場合）

```bash
cd src/csv2urdf/
python3 csv2urdf.py csv/sixdofarm.csv
```

---

## 実行方法（MoveIt + RViz）

```bash
ros2 launch sixdofarm_moveit_config demo.launch.py
```

RVizが起動し、ロボットが表示されます。Planningタブから「Plan and Execute」も可能です。

---

## 参考リンク

* [MoveIt 2公式サイト](https://moveit.ros.org/)
* [ttakubo/csv2urdf](https://github.com/ttakubo/csv2urdf)
* [ttakubo/sixdofarm\_moveit\_config](https://github.com/ttakubo/sixdofarm_moveit_config)

---

## 著者

亀山 恭佑（Kyosuke Kameyama）
