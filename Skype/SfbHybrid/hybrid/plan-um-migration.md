---
title: 規劃 Skype for Business Server 與 Exchange Server 移轉
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: 本主題涵蓋您需要考慮當您決定要將資料移轉您現有的 Skype for Business Server 或 Exchange Server 部署的最新版本或 Skype for Business Online 或 Exchange Online。
ms.openlocfilehash: ce2e0712c75e5aa052c7eff7667f09ff34c3908a
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265608"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>規劃 Skype for Business Server 與 Exchange Server 移轉

本主題涵蓋您需要考慮當您決定要將資料移轉您現有的 Skype for Business Server 或 Exchange Server 部署的最新版本或 Skype for Business Online 或 Exchange Online。 您可以移轉，以及何時，頻繁取決於什麼您已有設定好貴組織中。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>商務 Server 2019 中可用的功能變更 Exchange 2019 與 Skype

Exchange 2019 與 Skype for Business Server 2019，我們我們所支援的功能進行一些變更。

### <a name="unified-messaging-support-in-exchange-2019"></a>整合通訊支援在 Exchange 2019

整合通訊 (UM) 已在 Exchange 2019 中被取代。 這表示，Exchange 2019 已不再提供下列功能：

- 語音信箱
- 自動語音應答

如果您已部署 Exchange 2013 或 UM 服務中的 UM 角色在 Exchange 2016，而且您想要升級到 Exchange 2019，您需要將您的語音信箱移轉到 Office 365 中的 Microsoft 雲端語音信箱服務。 如果您想要將您的語音信箱移轉至雲端語音信箱，看看[Exchange 2013/Exchange 2016 與 Skype for Business 2015 來 Exchange 2019 與 Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)下一節。
> [!IMPORTANT]
> 如果使用者在 Exchange 2013 或 Exchange 2016 伺服器上的已啟用 UM 的信箱，不將它們移到 Exchange 2019 升級 Business Server 2019 skype 您 Skype for Business 伺服器與將使用者移至，以避免語音訊息中斷之前。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>PBX 支援在 Exchange 2019 與 Skype for Business Server 2019

雲端語音信箱不提供語音訊息專用交換機 (Pbx) 的功能。 如果您使用 Exchange Server 整合通訊的 Pbx，而且您想要升級至 Exchange Server 2019，必須採用下列其中一個部落格文章[Exchange 團隊部落格](https://blogs.technet.microsoft.com/exchange/)上的[新日期主題的工作階段邊界控制器支援在 Exchange Online 整合通訊](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)中所列的三個選項。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online UM 支援 Skype for Business Server 2019

與 Skype for Business Server 2019，我們可以從 Exchange Online UM 雲端語音信箱移。 當使用者移至 Skype for Business 2019 伺服器時，他們將自動開始使用雲端語音信箱時的主控語音信箱設定。 如果您目前使用 Exchange Online UM，您不需要執行任何以外的移動動作 Skype for Business Server 2019 若要開始使用雲端語音信箱使用者。 不過，有一些變更，您需要注意的功能：

- 組織自動語音應答是自動語音應答取代在 Exchange Online UM。
- 網頁型 Outlook 中的使用者語音信箱設定不適用於雲端語音信箱。

## <a name="on-premises-um-migration-scenarios"></a>內部部署 UM 移轉案例

我們支援下列案例可讓您將使用者移轉到 Exchange 2019 與雲端語音信箱。

- Exchange 2013/Exchange 2016 與 Skype for Business Server 2015 到 Exchange 2019 與 Skype for Business Server 2019
- Skype 至 Skype for Business Server 2019 與 Exchange 2013/Exchange 2016 的 Business Server 2015

下列案例需要沒有 PBX 或 SBC 設定為目前部署的一部分存在，並假設您已在內部部署 Exchange 伺服器上設定的 UM。 每個這些解決方案也假設您已決定要設定您內部部署的 Skype 商務伺服器與 Office 365 之間的混合部署。 如需 Skype for Business 混合式部署，請參閱[規劃混合式連線](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 與 Skype for Business 2015 到 Exchange 2019 與 Skype for Business 2019

在此案例中，您想要將現有的 Exchange 2013、 Exchange 2016 與 Skype for Business 2015 伺服器到 Exchange 2019 與 Skype for Business 2019 移轉。

本主題稍早所述，Exchange 2019 不再包含 UM 服務。 這表示，針對任何您想要移動到 Exchange 2019，您需要使用來取代的功能，由 UM 服務所提供的雲端語音信箱的信箱。 當您設定 「 Skype for Business Server 2019 以及它與 Office 365 之間的混合式部署時，雲端 Voicemail 會取代這些 Exchange UM 語音信箱服務。

在其中您將使用者移至 Exchange 2019 與 Skype for Business Server 2019 的順序很重要來確保語音信箱功能仍然可供所有使用者。 處理語音信箱時也取決於 Exchange 與 Skype for Business 信箱和使用者的所在位置。 看看下列表格，請參閱 < 支援的 Exchange 與 Skype for Business Server 哪些組合，且其中處理語音信箱。

| 信箱位於：            | 使用者位於用 Skype Server 2015 | 使用者位於 Skype for Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支援                           | 雲端語音信箱                          |

在開始移轉至 Skype for Business Server 2019 以及 Exchange 2019 之前，請謹記下列事項：

- 雲端語音信箱不支援組織的自動語音應答在 ga。 如果您想繼續可透過自動語音應答移至雲端語音信箱的信箱，您需要保留 UM 角色或可用的服務執行的至少一個 Exchange 2013 或 Exchange 2016 伺服器。
- 您必須設定至少一個 Skype for Business 2019 伺服器**並**將使用者移至該伺服器，才能將其信箱移到 Exchange 2019。 若要執行這項操作失敗，會導致這些信箱無法接收語音信箱訊息。
- 傳送語音信箱通話會將傳送到雲端語音信箱將會記錄。 通話結束之後，語音信箱訊息會傳送至內部部署 Exchange 2019 伺服器上的收件者的信箱。 您必須決定您的網際網路連線能力是否足以支援雲端語音信箱時，請考量此語音流量。

以下是完成此移轉的高階步驟。

1. 安裝及設定 Skype 商務 Server 2019 的新伺服器上。
2. 更新您的混合式部署組態，以包含新的 Skype for Business 2019 伺服器。
3. 安裝及設定新伺服器上的 Exchange Server 2019。
4. 將使用者從您 Skype for Business 2015 伺服器移至您 Skype for Business 2019 伺服器。
5. 每個使用者移至 Skype for Business Server 2019 使用雲端語音信箱設定裝載的語音信箱原則。
6. 將信箱從 Exchange 2013 或 Exchange 2016 伺服器移至您的 Exchange 2019 伺服器。
7. 最後一個使用者已移出其之後，解除委任您 Skype for Business 2015 伺服器。
8. 解除委任 Exchange 2013 或 Exchange 2016 伺服器之後的最後一個信箱已移出它們。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答時，繼續至少一個 Exchange 2013 或 Exchange 2016，執行及使用。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype 至 Skype for Business Server 2019 與 Exchange 2013/Exchange 2016 的 Business Server 2015

在此案例中，您想要移轉商務 2015年伺服器您現有商務用 Skype 至 Skype 商務 Server 2019，但保留在 Exchange 2013 或 Exchange 2016。

當商務用 Skype Server 2015 與 Skype for Business Server 2019 並存於相同的組織時，可順暢地搭配 Exchange UM，並以確保該語音信箱的雲端語音信箱正確傳遞至 Exchange 信箱。 Exchange UM 或雲端語音信箱處理語音信箱，需視使用者是否位在商務用 Skype Server 2015 或 Skype for Business Server 2019 上的方法而定：

- 如果使用者位於用 Skype Server 2015，Exchange UM 會處理的語音信箱訊息。
- 如果使用者位於 Skype for Business Server 2019，雲端語音信箱將會處理的語音信箱訊息。

不論是否 Exchange UM 或雲端語音信箱程序的語音信箱訊息，郵件會儲存在使用者的 Exchange 信箱。

在開始移轉至 Skype for Business Server 2019 之前，請謹記下列事項：

- 雲端語音信箱不支援組織的自動語音應答在 ga。 如果您想繼續可透過自動語音應答移至雲端語音信箱的信箱，您需要保留 UM 角色或可用的服務執行的至少一個 Exchange 2013 或 Exchange 2016 伺服器。
- 傳送語音信箱通話會將傳送到雲端語音信箱將會記錄。 通話結束之後，語音信箱訊息會傳送至內部部署 Exchange 伺服器上的收件者的信箱。 您必須決定您的網際網路連線能力是否足以支援雲端語音信箱時，請考量此語音流量。

以下是完成此移轉的高階步驟。

1. 安裝及設定 Skype 商務 Server 2019 的新伺服器上。
2. 更新您的混合式部署組態，以包含新的 Skype for Business 2019 伺服器。
3. 將使用者從您 Skype for Business 2015 伺服器移至您 Skype for Business 2019 伺服器。
4. 每個使用者移至 Skype for Business Server 2019 使用雲端語音信箱設定裝載的語音信箱原則。
5. 最後一個使用者已移出其之後，解除委任您 Skype for Business 2015 伺服器。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答時，繼續至少一個 Exchange 2013 或 Exchange 2016，執行及使用。
