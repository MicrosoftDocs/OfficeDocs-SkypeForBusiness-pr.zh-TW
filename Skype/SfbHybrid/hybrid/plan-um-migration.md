---
title: 規劃商務用 Skype 和 Exchange Server 的先決條件的移轉
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: 本主題涵蓋當您決定將現有的商務用 Skype Server或Exchange Server部署移轉至最新版本或商務用 Skype Online 或 Exchange Online 時，需要考慮的事項。
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486988"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>規劃商務用 Skype 和 Exchange Server 的先決條件的移轉

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主題涵蓋當您決定將現有的商務用 Skype Server或Exchange Server部署移轉至Exchange Online時，需要考慮的事項。 您可以移轉的內容和移轉時機，主要取決於您已在組織中設定的內容。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 商務用 Skype Server 2019 中的功能變更

在 Exchange 2019 和 商務用 Skype Server 2019 中，我們正在對支援的功能進行一些變更。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 中的整合通訊支援

整合通訊 (UM) 在 Exchange 2019 中已被取代。 這表示 Exchange 2019 不再提供下列功能：

- 語音信箱
- 自動語音應答

如果您已在 Exchange 2013 中部署 UM 角色，或在 Exchange 2016 中部署 UM 服務，而且想要升級至 Exchange 2019，您必須將語音信箱移轉至 Microsoft 365 或 Office 365 中的 Microsoft 雲端語音信箱 服務。 如果您想要將語音信箱移轉至 雲端語音信箱，請參閱下面的[Exchange 2013/Exchange 2016 和 商務用 Skype 2015 至 Exchange 2019 和 商務用 Skype 2019 一](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)節。
> [!IMPORTANT]
> 如果您 Exchange 2013 或 Exchange 2016 伺服器上的使用者具有啟用 UM 的信箱，請勿在您將商務用 Skype伺服器升級至 2019 商務用 Skype Server之前將其移至 Exchange 2019，並將使用者移至信箱以避免語音訊息中斷。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和 商務用 Skype Server 2019 中的 PBX 支援

雲端語音信箱不會將語音傳訊功能提供給私人分支交換 (PBX) 。 如果您使用 Exchange Server Unified Messaging for PBX，而且想要升級至 Exchange Server 2019 年，您必須採用部落格文章中列出的三個選項之一：在[Exchange Team 部落](https://blogs.technet.microsoft.com/exchange/)格上[Exchange Online整合通訊中停止支援會話邊界控制器的新日期](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online 2019 年 商務用 Skype Server UM 支援

在 2019 商務用 Skype Server，我們將從 Exchange Online UM 移至 雲端語音信箱。 當使用者移至 商務用 Skype 2019 伺服器時，他們會在針對託管語音信箱設定時自動開始使用雲端語音信箱。 如果您目前使用 Exchange Online UM，除了將使用者移至 商務用 Skype Server 2019 以開始使用 雲端語音信箱 之外，您不需要執行任何動作。 不過，您需要注意的功能有一些變更：

- 組織自動語音應答會取代 Exchange Online UM 中的自動語音應答。
- Outlook 網頁版中的使用者語音信箱設定不適用於雲端語音信箱。

## <a name="on-premises-um-migration-scenarios"></a>內部部署 UM 移轉案例

我們支援下列案例，可讓您將使用者同時移轉至 Exchange 2019 和 雲端語音信箱。

- Exchange 2013/Exchange 2016 和 商務用 Skype Server 2015 至 Exchange 2019 和 商務用 Skype Server 2019
- 商務用 Skype Server 2015 至 2019 年 商務用 Skype Server Exchange 2013/Exchange 2016

下列案例要求目前的部署中沒有 PBX 或 SBC 設定，並假設您已在內部部署 Exchange 伺服器上設定 UM。 這些解決方案也假設您已決定在內部部署商務用 Skype伺服器與 Microsoft 365 或 Office 365 之間設定混合式部署。 如需商務用 Skype混合式部署的詳細資訊，請參閱[規劃混合式連線](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和 商務用 Skype 2015 至 Exchange 2019 和 商務用 Skype 2019

在此案例中，您想要將現有的 Exchange 2013、Exchange 2016 和 商務用 Skype 2015 伺服器移轉至 Exchange 2019 和 商務用 Skype 2019。

如本主題稍早所述，Exchange 2019 不再包含 UM 服務。 這表示，對於您想要移至 Exchange 2019 的任何信箱，您都必須使用雲端語音信箱來取代 UM 服務所提供的功能。 當您設定 商務用 Skype Server 2019 和 Microsoft 365 或 Office 365 之間的混合式部署時，雲端語音信箱取代這些 Exchange UM 語音信箱服務。

您將使用者移至 Exchange 2019 和 商務用 Skype Server 2019 的順序，對於確保所有使用者都能使用語音信箱功能非常重要。 處理語音信箱的位置也取決於 Exchange 和商務用 Skype信箱和使用者的所在位置。 請查看下表，以查看支援哪些 Exchange 和 商務用 Skype Server 的組合，以及處理語音信箱的位置。

| 信箱位於：            | 使用者位於 2015 商務用 Skype Server | 使用者位於 2019 商務用 Skype Server  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支援                           | 雲端語音信箱                          |

開始移轉至 商務用 Skype Server 2019 和 Exchange 2019 之前，請記住下列事項：

- 您必須設定至少一部 商務用 Skype 2019 伺服器，**並將** 使用者移至該伺服器，才能將其信箱移至 Exchange 2019。 若無法這麼做，會導致這些信箱無法接收語音信箱訊息。
- 傳送至語音信箱的通話會傳送至將記錄的雲端語音信箱。 通話結束後，語音信箱會傳送至內部部署 Exchange 2019 伺服器上的收件者信箱。 當您判斷網際網路連線能力是否足以支援雲端語音信箱時，您必須將此語音流量納入考慮。

以下是完成此移轉的高階步驟。

1. 在新的伺服器上安裝和設定 商務用 Skype Server 2019。
2. 更新您的混合式部署組態，以包含新的 商務用 Skype 2019 伺服器。
3. 在新的伺服器上安裝和設定 Exchange Server 2019。
4. 將使用者從 商務用 Skype 2015 伺服器移至您的 商務用 Skype 2019 伺服器。
5. 設定每個移至 2019 商務用 Skype Server使用者的託管語音信箱原則，以使用 雲端語音信箱。
6. 將信箱從 Exchange 2013 或 Exchange 2016 伺服器移至 Exchange 2019 伺服器。
7. 在最後一個使用者移除 2015 伺服器之後，解除委任您的 商務用 Skype 2015 伺服器。
8. 在最後一個信箱移除之後，解除委任您的 Exchange 2013 或 Exchange 2016 伺服器。


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>商務用 Skype Server 2015 至 2019 年 商務用 Skype Server Exchange 2013/Exchange 2016

在此案例中，您想要將現有的 商務用 Skype 2015 伺服器移轉至 商務用 Skype Server 2019，但保留在 Exchange 2013 或 Exchange 2016 上。

當 商務用 Skype Server 2015 和 商務用 Skype Server 2019 共存于相同組織時，它們會順暢地與 Exchange UM 和 雲端語音信箱 合作，以確保語音信箱正確地傳遞至 Exchange 信箱。 Exchange UM 或 雲端語音信箱 處理語音信箱取決於使用者是位於 2015 商務用 Skype Server還是 2019 商務用 Skype Server：

- 如果使用者位於 商務用 Skype Server 2015，Exchange UM 將會處理語音信箱訊息。
- 如果使用者位於 2019 商務用 Skype Server，雲端語音信箱會處理語音信箱訊息。

無論 Exchange UM 或 雲端語音信箱 處理語音信箱訊息，訊息都會儲存在使用者的 Exchange 信箱中。

開始移轉至 2019 商務用 Skype Server之前，請記住下列事項：

- 傳送至語音信箱的通話會傳送至將記錄的雲端語音信箱。 通話結束後，語音信箱會傳送至內部部署 Exchange 伺服器上收件者的信箱。 當您判斷網際網路連線能力是否足以支援雲端語音信箱時，您必須將此語音流量納入考慮。

以下是完成此移轉的高階步驟。

1. 在新的伺服器上安裝和設定 商務用 Skype Server 2019。
2. 更新您的混合式部署組態，以包含新的 商務用 Skype 2019 伺服器。
3. 將使用者從 商務用 Skype 2015 伺服器移至您的 商務用 Skype 2019 伺服器。
4. 設定每個移至 2019 商務用 Skype Server使用者的託管語音信箱原則，以使用 雲端語音信箱。
5. 在最後一個使用者移除 2015 伺服器之後，解除委任您的 商務用 Skype 2015 伺服器。

