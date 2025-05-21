# カーソルに反応するウネウネ動く3D球体

## 機能

- Three.jsを使用した3Dワイヤーフレーム球体の表示
- カーソルの動きに反応して変形するアニメーション
- スムーズな動きを実現する補間処理
- タッチデバイス対応
- 光源の動的制御

## 技術スタック

- HTML5
- CSS3
- JavaScript
- [Three.js](https://threejs.org/) - 3Dグラフィックスライブラリ

## 使用方法

1. リポジトリをクローンまたはダウンロードします
2. `index.html`をブラウザで開きます
3. マウスを動かして球体の反応を確認します

```bash
git clone https://github.com/username/moving-ball.git
cd moving-ball
# ローカルサーバーで実行する場合（例：VS Codeの「Live Server」拡張機能など）
# または単純にindex.htmlをブラウザで開く
```

## カスタマイズ方法

### 球体の色を変更

```javascript
const material = new THREE.MeshPhongMaterial({
    color: 0x1a9dfb, // この値を変更（例：0xff0000で赤色）
    wireframe: true,
    transparent: true,
    opacity: 0.8,
    side: THREE.DoubleSide,
    specular: 0x4477ff,
    shininess: 100
});
```

### 変形の強さを調整

```javascript
// 時間ベースのアニメーション強度
const noise1 = 0.3 * Math.sin(time + i * 0.1) * Math.sin(original.y + time * 0.5);
// 0.3の値を大きくすると変形が強くなる

// マウス効果の強度
const mouseEffect = Math.max(0, 1 - distance) * 0.5;
// 0.5の値を大きくするとマウスの影響が強くなる
```

### 回転速度の調整

```javascript
sphere.rotation.x += 0.002; // X軸回転速度
sphere.rotation.y += 0.003; // Y軸回転速度
```

## ブラウザ互換性

- Chrome 最新版
- Firefox 最新版
- Safari 最新版
- Edge 最新版

## ライセンス

MIT

## 参考

- [DiverX](https://diver-x.jp/) - インスピレーション元
- [Three.js Documentation](https://threejs.org/docs/) - Three.jsの公式ドキュメント