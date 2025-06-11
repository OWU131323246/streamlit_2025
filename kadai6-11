import streamlit as st
import random

st.set_page_config(page_title="旅先診断アプリ", layout="centered")

st.title("🌍 あなたにぴったりの旅先診断アプリ")
st.write("いくつかの質問に答えるだけで、今のあなたにぴったりな旅行先をご紹介します。")

# 国と説明、スポットのみ（画像なし）
destinations = {
    "イタリア（ローマ）": {
        "description": "美食と芸術の国。歴史ある街並みとロマンチックな雰囲気が魅力。",
        "spots": ["コロッセオ", "トレビの泉", "バチカン市国"]
    },
    "日本（京都）": {
        "description": "伝統文化と自然に癒やされる旅。静かな時間を過ごしたい人に。",
        "spots": ["清水寺", "伏見稲荷大社", "金閣寺"]
    },
    "アメリカ（ニューヨーク）": {
        "description": "活気あふれる都市で刺激を求めるならここ！",
        "spots": ["タイムズスクエア", "セントラルパーク", "自由の女神"]
    },
    "バリ島": {
        "description": "ゆったりしたリゾートで癒しのひとときを。",
        "spots": ["ウブド", "タナロット寺院", "クタビーチ"]
    },
    "アイスランド": {
        "description": "大自然に囲まれて心も体もリフレッシュ。",
        "spots": ["ブルーラグーン", "ゴールデンサークル", "オーロラ鑑賞"]
    },
    "ニュージーランド": {
        "description": "星空、山、湖、動物…心を癒しながらもアクティブに過ごせます。",
        "spots": ["ミルフォード・サウンド", "ワイトモ洞窟", "ロトルア温泉"]
    },
    "フランス（パリ）": {
        "description": "芸術・文化・グルメの都。歴史と洗練が融合した旅を楽しめます。",
        "spots": ["エッフェル塔", "ルーブル美術館", "モンマルトルの丘"]
    },
    "韓国（ソウル）": {
        "description": "ショッピング、ストリートフード、韓流文化にどっぷり浸かる旅。",
        "spots": ["明洞", "景福宮", "東大門市場"]
    }
}

# 入力フォーム
with st.form("travel_form"):
    st.subheader("📝 あなたのことを教えてください")

    mood = st.radio(
        "今の気分は？",
        [
            "リラックスしたい",
            "自然に癒されたい",
            "刺激がほしい",
            "文化を感じたい",
            "美味しいものを食べたい"
        ],
        horizontal=True
    )

    season = st.selectbox("旅行に行くならどの季節？", ["春", "夏", "秋", "冬"])

    companion = st.radio(
        "誰と行く予定？",
        ["ひとり旅", "友達と", "家族と", "恋人と"],
        horizontal=True
    )

    duration = st.slider("旅行の日数は？（泊数）", min_value=1, max_value=14, value=3)

    submitted = st.form_submit_button("診断する")

# 診断結果表示
if submitted:
    st.subheader("🧳 診断結果")

    if mood == "リラックスしたい":
        result = random.choice(["バリ島", "日本（京都）"])
    elif mood == "自然に癒されたい":
        result = random.choice(["アイスランド", "ニュージーランド", "日本（京都）"])
    elif mood == "刺激がほしい":
        result = random.choice(["アメリカ（ニューヨーク）", "韓国（ソウル）"])
    elif mood == "文化を感じたい":
        result = random.choice(["フランス（パリ）", "イタリア（ローマ）", "日本（京都）"])
    elif mood == "美味しいものを食べたい":
        result = random.choice(["韓国（ソウル）", "イタリア（ローマ）"])
    else:
        result = random.choice(list(destinations.keys()))

    st.success(f"🎉 あなたにぴったりの旅先は... **{result}** です！")
    st.markdown(destinations[result]["description"])
    st.write(f"🕒 旅行期間：{duration}泊（{duration + 1}日間）を想定しています。")

    st.markdown("### 📍 おすすめスポット")
    for spot in destinations[result]["spots"]:
        st.write(f"- {spot}")

    if st.button("もう一度診断する"):
        st.experimental_rerun()
