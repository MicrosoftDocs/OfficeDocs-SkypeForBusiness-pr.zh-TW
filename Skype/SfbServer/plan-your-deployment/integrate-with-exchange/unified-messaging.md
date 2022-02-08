---
title: 規劃商務用 Skype 中的 Exchange 整合通訊整合
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要：在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請參閱本主題。
ms.openlocfilehash: b48ff4582cf9ef218c7b28abb9c52245e40a5214
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389075"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>規劃商務用 Skype 中的 Exchange 整合通訊整合

**總結：** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請複習本主題。

商務用 Skype Server 支援與 Exchange 整合通訊 (UM) 整合，以將語音訊息與電子郵件訊息結合成單一郵件基礎結構。 在 Exchange 中，Exchange 整合通訊 (UM) 是您可以安裝及設定的數個 Exchange 伺服器角色之一。

在 Microsoft Exchange Server 2013 和2016中，Exchange UM 在 Exchange 信箱伺服器上以服務方式執行。 針對商務用 Skype Server 企業語音部署，整合通訊會將語音訊息與電子郵件合併到單一存放區中，使用者可以從電話存取， (Outlook 語音存取) 或電腦。 整合通訊和商務用 Skype Server 搭配合作，為企業語音的使用者提供呼叫回應、Outlook 語音存取和自動語音應答服務。

> [!NOTE]
> 當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時，商務用 Skype Server 2019 仍可使用 Exchange UM。 因為 Exchange 2019 的支援變更，所以 Exchange UM 整合的目的是為了取代雲端語音信箱和雲端自動語音應答功能。  如需詳細資訊，請參閱[plan 雲端語音信箱 service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [plan 商務用 Skype Server and Exchange Server 遷移](../../../sfbhybrid/hybrid/plan-um-migration.md)。


若要在內部部署 Exchange UM 部署中支援這些功能，您必須執行下列其中一項：

- Microsoft Exchange Server 2010 或最新的 service pack (僅商務用 Skype Server 2015) 
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> 商務用 Skype Server 2019 中不再提供 Exchange 的整合通訊，其使用電話系統來錄製語音信箱訊息，然後在使用者的 Exchange 信箱中留下記錄。 如需詳細資訊，請參閱[Plan 雲端語音信箱 service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>整合整合通訊和商務用 Skype Server 的功能

商務用 Skype Server，企業語音使用 Exchange 整合通訊 (UM) 基礎結構，提供呼叫回應、來電通知、語音存取 (包括語音信箱) 和自動語音應答服務。

- **來電應答** 呼叫應答是代表使用者接收語音訊息，但來電並未接聽或占線。 它包含播放個人問候語、錄製郵件，並將郵件送出佇列以傳送至使用者的信箱，該信箱儲存在 Exchange 的信箱伺服器上。

    如果來電者留下訊息，該訊息就會傳送到使用者的收件匣。如果來電者選擇不留下任何訊息，則會在使用者的信箱中儲存未接來電通知。然後使用者可以使用 Microsoft Outlook 訊息和共同作業用戶端、Outlook Web Access、Exchange ActiveSync 技術或 Outlook Voice Access 存取自己的收件匣。可以使用與電子郵件類似的方式來顯示來電的主旨和優先順序。

- **Outlook 語音存取** Outlook 語音存取可讓企業語音使用者不僅可以存取語音信箱，還可以存取 Exchange 收件匣，包括電子郵件、行事曆和電話語音介面中的連絡人。 使用者存取號碼是由 Exchange UM 系統管理員所指派。

- **自動** 語音應答自動語音應答是一種 Exchange 的 UM 功能，可用來設定使用者可以撥出的電話號碼，以到達公司代表。 特別是，它提供了一系列的語音提示，可協助外部來電者瀏覽功能表系統。 可用的選項清單是由 Exchange um 管理員在 Exchange UM 伺服器上設定。

- **傳真服務** Exchange UM 包含傳真功能，可讓使用者在其 Exchange 信箱中接收傳入的傳真。 如需詳細資訊，請參閱 Microsoft Exchange Server 檔中的[整合通訊](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80))。

    > [!NOTE]
    > Exchange UM server 所提供的傳真服務無法在商務用 Skype Server 與 Microsoft Exchange Server 2010 整合的部署中使用，Exchange 2010 搭配最新的 service pack、Exchange 2013，或Exchange 2016。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>商務用 Skype Server 中內部部署整合通訊的元件和拓撲

### <a name="exchange-server-components"></a>Exchange Server 元件

若要提供[整合整合通訊的功能和商務用 Skype Server](#features-of-integrated-unified-messaging-and-skype-for-business-server)中所述的 Exchange UM 功能和服務，以企業語音組織中的使用者，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器，該伺服器主控使用者信箱，並提供電子郵件及語音信箱的單一存放位置。. Exchange UM 會在 Exchange 信箱和用戶端存取伺服器上以服務的身分執行。

如需 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱[部署 On-Premises Exchange UM，以提供 Lync Server 2013 預覽語音信箱](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。

### <a name="supported-topologies"></a>支援的拓撲

您可以在相同樹系或多個樹系中部署商務用 Skype Server 和 Exchange 整合通訊 (UM) 。 如果部署跨越多個樹系，您必須針對每個 Exchange UM 樹系執行 Exchange 的整合步驟。 此外，您必須將每個 Microsoft Exchange 樹系設定為信任商務用 Skype Server 樹系和商務用 Skype Server 樹系，以信任每個 Exchange UM 樹系。 除了這種樹系信任之外，所有使用者的 Exchange UM 設定都必須針對商務用 Skype Server 樹系中的使用者物件進行設定。

針對 Exchange UM 整合，商務用 Skype Server 支援下列拓撲：

- 單一樹系

- 單一網域 (亦即單一樹系搭配單一網域)。 商務用 Skype Server、Microsoft Exchange 和使用者都位於相同的網域中。

- 多重網域 (亦即，一個根網域搭配一或多個子網域)。 商務用 Skype Server，而 Microsoft Exchange 伺服器則會從您建立使用者的網域部署在不同的網域中。 您可以從支援的商務用 Skype Server 集區，將 Exchange UM 伺服器部署在不同的網域。

- 多重樹系 (亦即資源樹系)。 商務用 Skype Server 會部署在單一樹系中，然後將使用者散佈于多個樹系。 使用者的 Exchange UM 屬性必須複製到商務用 Skype Server 樹系。

    > [!NOTE]
    > Exchange 可以部署在多個樹系中。 每個 Exchange 組織都可以為其使用者提供 Exchange UM，也可以在商務用 Skype Server 的相同樹系中部署 Exchange um。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>整合內部部署整合通訊和商務用 Skype Server 的指導方針

以下是部署企業語音時所需考慮的指導方針和最佳作法：

> [!IMPORTANT]
> 只有在您同時使用 UCMA 4 時，才 Exchange 的整合通訊 (UM) 才能支援 IPv6。

- 部署商務用 Skype Server Standard Edition 伺服器或前端集區。

- 與 Exchange 系統管理員合作，確認每一個人將要執行的工作，以確保能夠順暢、成功地整合。

- 在每個 Exchange 整合通訊 (UM) 樹系中，部署 Exchange 信箱伺服器角色，以供您要為 Exchange UM 啟用使用者。 如需安裝 Exchange 伺服器角色的詳細資訊，請參閱 Microsoft Exchange Server 檔。

    > [!IMPORTANT]
    > 安裝 Exchange 整合通訊 (UM) 時，會將其設定為使用自我簽署憑證。 自我簽署憑證不會讓商務用 Skype Server 和 Exchange UM 彼此信任，這就是為何必須從兩部伺服器信任的憑證授權單位單位要求個別的憑證。

- 如果商務用 Skype Server 和 Exchange UM 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任商務用 Skype Server 樹系和商務用 Skype Server 樹系，以信任每個 Exchange 樹系。 此外，您也可以在商務用 Skype Server 樹系中的使用者物件上，設定使用者的 Exchange UM 設定，通常是使用腳本或跨樹系工具，例如 Identity 週期管理員 (ILM) 。

- 必要時，安裝 Exchange 管理主控台以便管理 Unified Messaging 伺服器。

- 取得 Outlook Voice Access 和自動語音應答的有效電話號碼。

- 如果您使用舊于 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 的 Exchange UM 版本，請 Exchange UM SIP URI 撥號對應表和企業語音撥號對應表的座標名稱。

### <a name="deploying-redundant-exchange-um-servers"></a>部署重複的 Exchange UM 伺服器

> [!IMPORTANT]
> 建議您為組織所設定的每個 Exchange UM SIP URI 撥號對應表，至少部署兩部執行 Exchange UM 服務的伺服器。 除了提供擴充的容量之外，部署冗余伺服器也可提供高可用性。 萬一發生伺服器故障，可將商務用 Skype Server 設定為容錯移轉至另一部伺服器。

以下範例設定可提供 Exchange UM 恢復能力。

**範例 1：Exchange UM 恢復能力**

![Exchange UM 恢復性圖表。](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

在範例 1 中，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。 在 Tukwila 中發生 Exchange UM 中斷的情況時，網域名稱系統 (DNS) 伺服器1和2的記錄應該分別設定為指向 servers 3 和4。 在都柏林中 Exchange UM 中斷的情況下，伺服器3和4的 DNS A 記錄應該設定為分別指向 servers 1 和2。

> [!NOTE]
> 在範例1中，您也應該在每個 Exchange UM 伺服器上指派下列其中一個憑證：在 [主體別名] 中使用具有萬用字元的憑證 (san) 或將完整功能變數名稱 (放在 san 中四個) UM 伺服器的每一個 FQDN Exchange。

**範例 2：Exchange UM 恢復能力**

![Exchange UM 恢復性圖表。](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

在範例 2 中，於正常運作情況下，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。這四部伺服器均包含在 Tukwila 使用者的 SIP URI 撥號對應表中，不過伺服器 3 和 4 均已停用。當 Tukwila 的 Exchange UM 伺服器發生如停止運作等的情況時，應停用 Exchange UM 伺服器 1 和 2 並啟用 Exchange UM 伺服器 3 和 4，以將 Tukwila Exchange UM 的流量路由傳送至 Dublin 的伺服器。

如需如何在 Exchange 2013 上啟用或停用整合通訊的詳細資訊，請參閱將[Exchange 2013 UM 與 Lync Server 整合](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help)。 提供的資訊平均套用至商務用 Skype Server。

如需如何在 Microsoft Exchange Server 2010 上啟用或停用整合通訊的詳細資訊，請參閱：

- [啟用 Exchange 2010 的整合通訊](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [停用 Exchange 2010 的整合通訊](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 2019 中不再出現 Exchange 整合通訊，如果您有 Exchange 2019，而且想要使用相同的功能，您必須使用[計畫雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述的雲端語音信箱服務。


## <a name="see-also"></a>另請參閱

[整合內部部署整合通訊和商務用 Skype 的部署程式概述](deployment-overview.md)