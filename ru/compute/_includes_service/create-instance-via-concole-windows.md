1. Откройте каталог, в котором будет создана виртуальная машина.
1. Нажмите кнопку **Создать ресурс**.
1. Выберите **Виртуальная машина**.
1. В поле **Имя** введите имя виртуальной машины.

    [!INCLUDE [name-format](../../_includes/name-format.md)]

    [!INCLUDE [name-fqdn](../../_includes/compute/name-fqdn.md)]

1. Выберите [зону доступности](../../overview/concepts/geo-scope.md), в которой будет находиться виртуальная машина.
1. Выберите один из публичных [образов](../operations/images-with-pre-installed-software/get-list.md) на базе операционной системы Windows.
1. В блоке **Вычислительные ресурсы**:
    - Выберите [платформу](../concepts/vm-platforms.md).
    - Укажите необходимое количество vCPU и объем RAM.
1. В блоке **Сетевые настройки** нажмите кнопку **Добавить сеть**.
1. В открывшемся окне выберите, к какой подсети необходимо подключить виртуальную машину при создании.
1. В поле **Публичный адрес** выберите:
    - **Автоматически** — чтобы назначить публичный IP-адрес автоматически. Адрес выделяется из пула адресов Яндекс.Облака.
    - **Список** — чтобы выбрать публичный IP-адрес из списка статических адресов. Подробнее читайте в разделе [[!TITLE]](../../vpc/operations/set-static-ip.md) документации сервиса [!KEYREF vpc-name].
    - **Без адреса** — чтобы не назначать публичный IP-адрес.
1. При создании виртуальной машины в операционной системе будет автоматически создан пользователь `Administrator`. В поле **Пароль** задайте пароль для этого пользователя, с которым можно будет войти на виртуальную машину по RDP.

    [!INCLUDE [password-requirements](../../_includes/compute/password-requirements.md)]

1. Нажмите кнопку **Создать ВМ**.
