4 пода в нормальном режиме (по нагрузочным тестам), HPA сделает 2 без нагрузки и 6 максимальный лимит при нагрузке. Но есть мысль что должно быть 3 раз зоны три, не хватает деталей.

PodAntiAffinity распределяет поды по разным нодам. NodeAffinity распределяет по зонам доступности. Минимум 2 пода ночью для сохранения отказоустойчивости

Запросы CPU выше среднего потребления для быстрой инициализации. Лимиты с запасом для обработки пиков. Память фиксирована согласно требованиям.

HPA с плавным уменьшением реплик ночью. Быстрое увеличение при дневной нагрузке. Стабилизационные окна для плавного масштабирования

Длинные таймауты для долгой инициализации. RollingUpdate с гарантией доступности

Минимум реплик в периоды низкой нагрузки - 2. Плавное scale-down при падении нагрузки
