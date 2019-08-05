---
title: Lync Server 2010 的前端一般設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: '您可以編輯或設定下列屬性, 以編輯前端伺服器或頂層端池的屬性。 [設定] 頁面分為下列幾個區段:'
ms.openlocfilehash: b0ee8a2d0081d937bf93d4a638e4f56b1cc79134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189919"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的前端一般設定擴展器

您可以編輯或設定下列屬性, 以編輯前端伺服器或頂層端池的屬性。 [設定] 頁面分為下列幾個區段:

 **一般**

- **FQDN**: 前端伺服器或前端池的完整功能變數名稱。

- 選取 [**使用所有已設定的 IP 位址**], 以使用在前端伺服器或前端池上設定的所有位址。

    > [!IMPORTANT]
    > 如果您 collocate 前端伺服器或頂層端池中的中繼伺服器, 則不應選取此選項。 中繼伺服器與前端伺服器需要專用的 IP 位址來進行通訊。

- 選取 [**將服務使用限制為選取的 IP 位址**], 然後**** 輸入 Ip 位址作為 [前端伺服器] 或 [前端] 池與其余部署的通訊。 輸入**PSTN ip 位址**與中繼伺服器相關聯的 IP 位址。

    **功能與功能**

- **會議**: 如果您想要在部署中執行會議功能, 請選取此核取方塊。 會議包括音訊、影片、應用程式共用、桌面共用和網路會議。 您將需要建立並關聯 Office Web Apps Server for Web 會議 (在這個 [屬性] 頁面稍後定義)。

- 如果您選取 [會議], 則可以選取 **[撥入 (PSTN) 會議**]。 選取核取方塊以啟用電話撥入式會議功能。

- 如果您想要部署功能, 請選取 [**企業語音**], 以啟用 Lync Server 2013 作為使用 IP 語音 (VoIP) 技術的電話語音系統, 包括部署手持電話、SIP trunks 或公開的選項。根據設計與需求, 以結合或獨立的方式, 使用中繼伺服器、PSTN 閘道和 IP PBX 來交換電話網絡連線。 如需企業語音的詳細資訊, 請參閱[商務用 Skype Server 2015 中的](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)[企業語音](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)及企業語音規劃

    **關聯**

- **Sql server store**: sql SERVER 的 FQDN (以及可選擇的命名實例) 與前端伺服器或前端池相關聯。 您可以從清單中選取 [SQL Server store], 或按一下 [**新增**] 以建立新的 sql server store

- 檔案**存放區**: 您可以針對 Lync server 2013 為複製、會議目錄及其他`\\<FQDN of server>\<share name>`用途所建立及使用的共用檔案, 選取該伺服器和共用 (格式) 的 FQDN, 該檔案將充當檔案存放位置。 您可以從清單中選取檔案存放區, 或按一下 [**新增**] 來建立新的檔案存放區。

- 選取 [**關聯存檔伺服器**] 核取方塊, 以啟用此前端伺服器或頂層池的存檔伺服器。 選取核取方塊之後, 您會從清單中選取現有的封存伺服器, 或按一下 [**新增**], 建立新的封存伺服器的定義。

- 選取 [**關聯監視伺服器**] 核取方塊, 為此前端伺服器或頂層池啟用監視伺服器。 選取核取方塊之後, 您會從清單中選取現有的監視伺服器, 或按一下 [**新增**], 建立新的監視伺服器的定義。

- 選取 [**關聯邊緣池] (適用于 [媒體元件**] 核取方塊), 以針對此前端伺服器或頂層池啟用邊緣伺服器。 選取核取方塊之後, 您會從清單中選取現有的邊緣伺服器或文件庫, 或按一下 [**新增**], 建立新的邊緣伺服器或池的定義。

  **恢復**

- 選取 [**關聯的備份註冊機構**區] 核取方塊, 以從清單中選取要作為備份註冊機構的 [前端伺服器] 或 [前端] 池 (也就是, 在主機未能

- 如果您已選取 [關聯的備份註冊機構], 並選取了備份註冊機構, 您可以選取 [**自動容錯移轉] 和 [語音回切**] 的核取方塊。 您現在可以定義**語音容錯移轉偵測 (秒)** 與**語音回切間隔 (秒)** 的數位屬性。 如需詳細資訊, 請參閱[規劃企業語音復原](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Web 服務**

- 若要設定**內部 web 服務**, 您需要定義**HTTP**和**HTTPS**的**偵聽埠**。 根據預設, 這些分別是 TCP 埠80和 TCP 埠443。 您也可以設定**HTTP**和**HTTPS**的**已發佈埠**。 根據預設, 這些分別是 TCP 埠80和 TCP 埠443。 根據您的內部 web 服務設定及使用負載平衡器 (硬體負載平衡器和 DNS 負載平衡), 調整埠值以定義偵聽與已發佈的埠。

    > [!IMPORTANT]
    > 內部 web 服務與已定義的偵聽與已發佈埠都適用于內部用戶端和裝置。 外部用戶端和裝置會使用外部 web 服務偵聽與已發佈的埠, 以及已定義的外部 web 服務完整功能變數名稱 (FQDN)。

- 若要設定**外部 web 服務**, 您需要定義**HTTP**和**HTTPS**的**偵聽埠**。 根據預設, 這些分別是 TCP 埠80和 TCP 埠443。 您也可以設定**HTTP**和**HTTPS**的**已發佈埠**。 根據預設, 這些分別是 TCP 埠80和 TCP 埠443。 根據您的內部 web 服務設定及使用負載平衡器 (硬體負載平衡器和 DNS 負載平衡), 調整埠值以定義偵聽與已發佈的埠。

    > [!IMPORTANT]
    > 外部 web 服務和已定義的偵聽與已發佈埠都適用于外部用戶端和裝置。 外部用戶端和裝置使用外部 web 服務偵聽與已發佈的埠, 通常是由您的反向 proxy 所定義, 以及已定義的外部 web 服務完整功能變數名稱 (FQDN)。 外部 web 服務 FQDN 與簡單 Url 的關聯定義了外部用戶端將用來存取外部使用者和裝置可用服務的統一資源定位器 (URL) 位址。 如需簡單 Url 的詳細資訊, 請參閱[規劃簡單 url](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。

  **中繼伺服器**

- 若要為 collocated 中繼伺服器 (也就是在前端伺服器或頂層端池上部署的中繼伺服器) 設定**轉送伺服器**屬性, 請選取 [**已啟用 collocated 中繼伺服器**]。

- 若要定義 collocated 中繼伺服器的**偵聽埠**, 您可以輸入 Collocated 轉送伺服器所偵聽的**TLS**和**TCP**埠值。 根據預設, TLS 定義為 TCP 埠5067。

- 若要為中繼伺服器定義 TCP 埠值, 請選取 [**啟用 TCP 埠**] 核取方塊。 根據預設, 中繼伺服器會透過 TCP 通訊協定使用傳輸層安全性 (TLS)。 只有在啟用 [啟用 TCP 埠] 選項時, 才能使用 TCP 埠。

    > [!NOTE]
    > 這是選擇性設定, 您應該參考閘道或 PSTN 的需求, 以判斷您是否需要這項功能。 依預設，TCP 連接埠的值為 5068。

- 您可以定義與 collocated 中繼伺服器相關聯的 trunks。 如果已經定義主幹，可以將其用來與中繼伺服器相關聯。

    如果您有多個與中繼伺服器關聯的閘道, 您可以指定預設閘道, 方法是選取要設為預設值的閘道, 然後按一下 [**設為預設值**]。 如果您選擇移除目前的預設閘道, 請選取閘道, 然後按一下 [ **Unmake 預設值**]。

> [!IMPORTANT]
> 如果您在此對話方塊中變更屬性, 您必須發佈拓撲, 並在所有受影響的伺服器上執行商務用 Skype Server 部署嚮導。 在發佈新的拓撲之後, 您必須執行商務用 Skype Server 部署嚮導所受影響伺服器的清單, 才能成為成功拓撲發佈摘要畫面上的連結。 如需發佈更新拓撲的詳細資料, 請參閱[發佈拓撲](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)。 如需商務用 Skype Server 部署嚮導的詳細資料, 請參閱[Lync server 系統管理工具](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。

按一下 **[確定]** 儲存並提交您對拓撲檔所做的變更。

按一下 [**取消**] 放棄變更, 然後關閉前端伺服器或頂層端池的**編輯屬性**。

按一下**** [說明] 以閱讀此說明主題。

## <a name="see-also"></a>另請參閱

[定義及設定前端池或標準版伺服器](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
