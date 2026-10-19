## 🏎️ Araba Yarışı

Bu meydan okumada, Gymnasium'dan [Car Racing ortamı](https://gymnasium.farama.org/environments/box2d/car_racing/) ile çalışacaksınız. Görev, prosedürel olarak oluşturulan bir pistte arabayla sürüş yaparak, yolda kalırken turları verimli bir şekilde tamamlamaktır.

İki tür pekiştirmeli öğrenme ajanı eğiteceksiniz: bir **DQN ajanı** ve bir **PPO ajanı**.

🚧 Başlamadan önce: ilk projede gerekli paketleri kurduğunuzdan emin olun

## Çalışma Notları

Bu proje, Gymnasium ve Stable Baselines3 ile `CarRacing-v3` ortamında DQN ve PPO ajanlarını eğitir ve karşılaştırır. Şablon yönerge notebook'u yerine kendi notebook'um kullanıldı.

1. Ortam: Workintech'in `S19D41.0-S-reinforcement-env` deposundaki `requirements.txt` ile kurulan `reinforcement-env` sanal ortamı (Python 3.12.9). Proje klasöründe `pyenv local reinforcement-env` ile etkinleştirilir.
2. `jupyter notebook` ile notebook'u aç. Dikkat: iki 100.000 adımlık eğitim hücresi CPU'da yaklaşık 55 dakika (DQN) ve 32 dakika (PPO) sürer, "Run All" yapmadan önce bunu bil.
3. Eğitilen modeller (`dqn_car_racing.zip`, `ppo_car_racing.zip`) repoya eklenmedi, `.gitignore` içindedir. Notebook çalıştırılınca yeniden oluşur.

Özet: DQN sürekli eylem uzayında çalışmadığı için eylemler 5 ayrık eyleme çevrildi. 5 pistte deterministik değerlendirmede ortalama ödül DQN için 296.9, PPO için 374.7 çıktı, ama PPO'nun ortalaması tek bir pistten (848.3) geliyor ve 5 pistle üstünlük kanıtlanamıyor. 10 değerlendirme bölümünün hiçbiri tur tamamlamadı, hepsi 1000 adımlık zaman sınırında bitti. Ayrıntılar ve sınırlılıklar notebook'un yorum bölümünde.
