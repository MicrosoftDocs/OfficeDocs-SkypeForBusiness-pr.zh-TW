---
title: 在商務用 Skype 中規劃 Exchange 整合訊息整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要：在規劃將商務用 Skype 伺服器與 Exchange 2013 或2016整合時，請複習本主題。
ms.openlocfilehash: bed73151b1010dd287c21ea55372e4eb18117665
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772616"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>在商務用 Skype 中規劃 Exchange 整合訊息整合

**摘要：** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請複習本主題。

商務用 Skype 伺服器支援與 Exchange 整合通訊（UM）整合，以將語音訊息和電子郵件訊息結合到單一訊息基礎結構。 在 Exchange 中，Exchange 整合通訊（UM）是您可以安裝及設定的數個 Exchange 伺服器角色之一。

在 Microsoft Exchange Server 2013 和2016中，Exchange UM 在 Exchange 信箱伺服器上以服務的方式執行。 針對商務用 Skype Server 企業版語音部署，整合的訊息結合了語音訊息和電子郵件訊息，以便讓使用者能夠從電話（Outlook 語音存取）或電腦存取單一商店。 整合通訊與商務用 Skype 伺服器共同作業，為企業語音的使用者提供呼叫應答、Outlook 語音存取及自動助理服務。

> [!NOTE]
> 當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時，Exchange UM 仍可在商務用 Skype Server 2019 中使用。 由於 Exchange 2019 中的支援變更，因此需要取消 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。  如需詳細資訊，請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)並[規劃商務用 Skype Server 和 Exchange server 遷移](../../../sfbhybrid/hybrid/plan-um-migration.md)。


若要在內部部署 Exchange UM 部署中支援這些功能，您必須執行下列其中一項操作：

- Microsoft Exchange Server 2010 或最新 service pack （僅適用于商務用 Skype Server 2015）
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> 在商務用 Skype Server 2019 中，Exchange 整合的郵件功能已不再提供，因為它會使用電話系統來錄製語音信箱訊息，然後將錄製保留在使用者的 Exchange 信箱中。 如需詳細資訊，請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>整合式整合訊息及商務用 Skype 伺服器的功能

商務用 Skype Server、企業語音使用 Exchange 整合訊息（UM）基礎結構來提供通話應答、呼叫通知、語音存取（包括語音信箱）及自動助理服務。

- **呼叫應答**[通話接聽] 是代表不接聽或忙碌通話的使用者接收語音訊息。 它包括播放個人問候語、記錄郵件，以及提交郵件以傳送到使用者的信箱，而該信箱會儲存在 Exchange 信箱伺服器上。

    如果來電者離開郵件，郵件會傳送到使用者的 [收件匣]。 如果來電者選擇不留下訊息，就會將未接來電通知儲存在使用者的信箱中。 然後，使用者就可以使用 Microsoft Outlook 的訊息與共同作業用戶端、Outlook Web Access、Exchange ActiveSync 技術或 Outlook 語音存取來存取收件匣。 通話的主旨與優先順序可以以與電子郵件類似的方式顯示。

- **Outlook 語音存取**Outlook 語音存取可讓企業語音使用者存取除語音信箱以外的 [Exchange 收件匣]，包括來自電話介面的電子郵件、行事曆和連絡人。 訂閱者存取號碼是由 Exchange UM 管理員指派。

- **自動**語音應答自動語音應答是一種 Exchange UM 功能，可讓您用來設定使用者可以撥打電話給公司代表的電話號碼。 特別是，它提供一系列的語音提示，協助外部呼叫者流覽功能表系統。 可用選項的清單是由 Exchange UM 管理員在 Exchange UM 伺服器上設定。

- **傳真服務**Exchange UM 包括 [傳真] 功能，可讓使用者在其 Exchange 信箱中接收傳入的傳真。 如需詳細資訊，請參閱 Microsoft Exchange Server 檔中的[統一訊息](https://go.microsoft.com/fwlink/p/?linkId=135652)。

    > [!NOTE]
    > Exchange UM 伺服器提供的傳真服務無法在與 Microsoft Exchange Server 2010 2010 （含最新 service pack、Exchange 2013 或 Exchange 2016）整合的商務用 Skype Server 部署中使用。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>商務用 Skype Server 中內部部署整合訊息的元件與拓撲

### <a name="exchange-server-components"></a>Exchange Server 元件

您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取，才能提供整合式整合[訊息及商務用 Skype Server 功能](#features-of-integrated-unified-messaging-and-skype-for-business-server)中所述的 Exchange UM 功能及服務。伺服器會寄存使用者信箱，並提供單一儲存空間來存放電子郵件和語音信箱。 Exchange UM 在 Exchange 信箱和用戶端存取伺服器上以服務的方式執行。

如需 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱[部署內部部署 EXCHANGE UM，以提供 Lync Server 2013 預覽語音信箱](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。

### <a name="supported-topologies"></a>支援的拓撲

您可以在同一個目錄林中或多個目錄林中部署商務用 Skype Server 和 Exchange 整合通訊（UM）。 如果部署跨越多個目錄林，您必須針對每個 Exchange UM 目錄林執行 Exchange 整合步驟。 此外，您必須將每個 Microsoft Exchange 林設定為信任商務用 Skype Server 林與商務用 Skype 伺服器林，以信任每個 Exchange UM 林。 除了此目錄林信任之外，所有使用者的 Exchange UM 設定都必須在商務用 Skype Server 林中的使用者物件上設定。

商務用 Skype 伺服器支援適用于 Exchange UM 整合的下列拓朴：

- 單一目錄林

- 單一網域（也就是單一網域的單一林）。 商務用 Skype Server、Microsoft Exchange 和使用者都位於同一個網域中。

- 多個網域（也就是包含一或多個子域的根網域）。 商務用 Skype Server 及 Microsoft Exchange 伺服器會從您建立使用者的網域部署在不同的網域中。 Exchange UM 伺服器可以在他們支援的商務用 Skype 伺服器池以外的不同網域中部署。

- 多個目錄林（也就是資原始目錄林）。 商務用 Skype 伺服器會部署在單一目錄林中，然後使用者會分佈在多個目錄林。 使用者的 Exchange UM 屬性必須複製到商務用 Skype Server 林。

    > [!NOTE]
    > Exchange 可以在多個林中部署。 每個 Exchange 組織都可以為其使用者提供 Exchange UM，或者 Exchange UM 可以部署在與商務用 Skype Server 相同的林中。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>整合內部部署整合通訊和商務用 Skype 伺服器的指導方針

下列是在您部署企業語音時要考慮的指導方針和最佳做法：

> [!IMPORTANT]
> Exchange 整合通訊（UM）只有在您同時使用 UCMA 4 時才支援 IPv6。

- 部署商務用 Skype Server 標準版伺服器或前端池。

- 與 Exchange 管理員共同確認您將執行的工作，以確保順利且順利地整合。

- 在您要啟用 Exchange UM 使用者的每個 Exchange 整合通訊（UM）目錄林中，部署 Exchange 信箱伺服器角色。 如需安裝 Exchange server 角色的詳細資料，請參閱 Microsoft Exchange Server 檔。

    > [!IMPORTANT]
    > 安裝 Exchange 整合通訊（UM）後，系統會將它設定為使用自行簽署式認證。 自行簽署式認證不會啟用商務用 Skype Server 與 Exchange UM 互相信任，這就是為什麼必須從兩個伺服器信任的憑證授權單位要求個別憑證的原因。

- 如果商務用 Skype Server 和 Exchange UM 已安裝在不同的林中，請將每個 Exchange 林設定為信任商務用 Skype Server 林與商務用 Skype 伺服器林，以信任每個 Exchange 目錄林。 此外，您也可以在商務用 Skype Server 林中的使用者物件上設定使用者的 Exchange UM 設定，通常是使用腳本或跨林工具（例如 [身分識別週期管理員（ILM）]）。

- 如有需要，請安裝 Exchange 管理主控台來管理您的整合郵件伺服器。

- 取得 Outlook 語音存取和自動語音應答的有效電話號碼。

- 如果您使用的 Exchange UM 版本早于 Microsoft Exchange Server 2010 Service Pack 1 （SP1），請調整 Exchange UM SIP URI 撥號方案和企業語音撥號方案的名稱。

### <a name="deploying-redundant-exchange-um-servers"></a>部署重複的 Exchange UM 伺服器

> [!IMPORTANT]
> 我們建議您在針對您的組織設定的每個 Exchange UM SIP URI 撥號方案中，部署至少有兩個 Exchange UM 服務正在執行的伺服器。 除了提供擴充的容量之外，部署冗余伺服器也提供高可用性。 當伺服器發生故障時，可將商務用 Skype 伺服器設定為容錯移轉到另一個伺服器。

下列範例配置提供 Exchange UM 復原。

**範例1： Exchange UM 復原**

![Exchange UM 復原圖表](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

在範例1中，Exchange UM 伺服器1和2在 Tukwila 資料中心中啟用，而在都柏林資料中心啟用 Exchange UM 伺服器3和4。 在 Tukwila 中發生 Exchange UM 停用時，網域名稱系統（DNS）會將伺服器1和2的記錄分別設定為指向 [伺服器 3] 和 [4]。 在都柏林中發生 Exchange UM 停用時，伺服器3和4的 DNS A 記錄應該設定為分別指向 [伺服器 1] 和 [2]。

> [!NOTE]
> 例如，您也應該在每個 Exchange UM 伺服器上指派下列其中一個憑證：在 [Subject 替換名稱（SAN）] 中使用萬用字元，或將四個 Exchange UM 伺服器的完整功能變數名稱（FQDN）放在 SAN 中。

**範例2： Exchange UM 復原**

![Exchange UM 復原圖表](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

在範例2的 [一般操作條件] 下，Exchange UM 伺服器1和2在 Tukwila 資料中心中啟用，且在都柏林資料中心啟用 Exchange UM 伺服器3和4。 所有四個伺服器都包含在 Tukwila 使用者的 SIP URI 撥號計畫中;不過，伺服器3和4會停用。 例如，在 Tukwila 中發生 Exchange um 停用時，應該停用 exchange UM 伺服器1和2，然後啟用 Exchange UM 伺服器3和4，以便將 Tukwila Exchange UM 流量路由到都柏林中的伺服器。

如需有關如何啟用或停用 Exchange 2013 整合訊息的詳細資訊，請參閱將[Exchange 2013 UM 與 Lync Server 整合](https://go.microsoft.com/fwlink/p/?LinkId=265372)。 所提供的資訊同樣適用于商務用 Skype 伺服器。

如需有關如何啟用或停用 Microsoft Exchange Server 2010 整合訊息的詳細資訊，請參閱：

- [在 Exchange 2010 上啟用整合訊息](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [停用 Exchange 2010 上的整合訊息](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 整合訊息在 Exchange 2019 中已不存在，如果您有 Exchange 2019，而且您想要使用相同的功能，您需要使用雲端語音信箱服務（在[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述）。


## <a name="see-also"></a>另請參閱

[整合內部部署整合訊息與商務用 Skype 的部署程式概述](deployment-overview.md)
