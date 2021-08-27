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
description: 本主題涵蓋當您決定將現有的商務用 Skype Server 或 Exchange Server 部署遷移至最新版本，或是商務用 Skype 線上或 Exchange Online 時，所需考慮的事項。
ms.openlocfilehash: edc6256bc9e366b4ee75a637c41141ec3d435da2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596117"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>規劃商務用 Skype 和 Exchange Server 的先決條件的移轉

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主題涵蓋當您決定要將現有的商務用 Skype Server 或 Exchange Server 部署遷移至 Exchange Online 時，需要考慮的事項。 您可以遷移的功能和時間取決於您已在組織中設定的專案。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和商務用 Skype Server 2019 中的功能變更

使用 Exchange 2019 和商務用 Skype Server 2019，我們將對我們支援的功能進行一些變更。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 的整合通訊支援

Exchange 2019 已棄用整合通訊 (UM) 。 這表示 Exchange 2019 不再提供下列功能：

- 語音信箱
- 自動語音應答

如果您已在 Exchange 2013 中部署 um 角色，或在 Exchange 2016 中 Microsoft 雲端語音信箱 um 服務，且您想升級至 Exchange 2019，您必須將語音信箱遷移至 Microsoft 365 或 Office 365 中的服務。 如果您想要將語音信箱遷移至雲端語音信箱，請參閱[Exchange 2013/Exchange 2016 及商務用 Skype 2015，以 Exchange 2019 及商務用 Skype 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)區段。
> [!IMPORTANT]
> 如果您 Exchange 2013 或 Exchange 2016 server 上的使用者有已啟用 UM 的信箱，請不要將商務用 Skype 伺服器移至 Exchange 2019，再升級伺服器以商務用 Skype Server 2019，並將使用者移至其中，以避免語音訊息中斷。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和商務用 Skype Server 2019 中的 PBX 支援

雲端語音信箱不會提供語音訊息功能到私人分支交換 (PBXs) 。 如果您要針對 PBXs 使用 Exchange Server 整合通訊，而且想要升級至 Exchange Server 2019，您必須採用博客文章中所列的三個選項之一，以在[Exchange 小組博客](https://blogs.technet.microsoft.com/exchange/)上的[Exchange Online 整合通訊中終止會話邊界控制器的支援](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online商務用 Skype Server 2019 中的 UM 支援

使用商務用 Skype Server 2019，我們正在從 Exchange Online UM 移至雲端語音信箱。 當使用者移至商務用 Skype 2019 伺服器時，他們會在設定為主控語音信箱時，自動開始使用雲端語音信箱。 如果您目前使用 Exchange Online UM，您不需要執行除了移動使用者以外的任何動作，以商務用 Skype Server 2019 開始使用雲端語音信箱。 不過，您需要注意的功能有一些變更：

- 組織自動語音應答是 Exchange Online UM 中的自動語音應答取代。
- 網頁 Outlook 中的使用者語音信箱設定不適用於雲端語音信箱。

## <a name="on-premises-um-migration-scenarios"></a>內部部署 UM 遷移案例

我們支援下列案例，可讓您將使用者遷移至 Exchange 2019 及雲端語音信箱。

- Exchange 2013/Exchange 2016 和商務用 Skype Server 2015，Exchange 2019 及商務用 Skype Server 2019
- 商務用 Skype Server 2015 至商務用 Skype Server 2019 搭配 Exchange 2013/Exchange 2016

在下列情況下，您目前的部署中不會存在 PBX 或 SBC 設定，假設您已在內部部署 Exchange 伺服器上設定 UM。 這兩種方案也會假設您已決定在內部部署商務用 Skype 伺服器與 Microsoft 365 或 Office 365 之間設定混合式部署。 如需商務用 Skype 混合式部署的詳細資訊，請參閱[規劃混合](plan-hybrid-connectivity.md)式連線。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和商務用 Skype 2015，Exchange 2019 及商務用 Skype 2019

在此案例中，您想要將現有的 Exchange 2013、Exchange 2016 及商務用 Skype 2015 伺服器遷移至 Exchange 2019 和商務用 Skype 2019。

如本主題稍早所述，Exchange 2019 不再包含 UM 服務。 這表示，針對您想要移至 Exchange 2019 的任何信箱，您必須使用雲端語音信箱取代 UM 服務所提供的功能。 當您設定商務用 Skype Server 2019 以及其與 Microsoft 365 或 Office 365 之間的混合式部署時，雲端語音信箱會取代這些 Exchange UM 語音信箱服務。

您將使用者移至 Exchange 2019 和商務用 Skype Server 2019 的順序，對於確保所有使用者都能繼續使用語音信箱功能是很重要的。 郵件語音處理的位置也取決於 Exchange 和商務用 Skype 信箱和使用者所在的位置。 請查看下表，查看支援哪些 Exchange 和商務用 Skype Server 組合，以及處理語音信箱的方式。

| 信箱位於：            | 使用者位於商務用 Skype Server 2015 | 使用者位於商務用 Skype Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支援                           | 雲端語音信箱                          |

在您開始遷移以商務用 Skype Server 2019 及 Exchange 2019 之前，請記住下列事項：

- 雲端語音信箱不支援正式發行的組織自動語音應答。 如果您想要將信箱移至雲端語音信箱以繼續透過自動語音應答取得，您必須至少有一個 Exchange 2013 或 Exchange 2016 server 執行 UM 角色或服務。
- 您必須在將使用者移至 Exchange 2019 之前，至少設定一部商務用 Skype 2019 server **，並** 將使用者移至該伺服器。 若失敗，將會導致這些信箱無法接收語音信箱訊息。
- 傳送至語音信箱的來電會轉接至要記錄的雲端語音信箱。 通話結束後，語音信箱訊息會傳送至內部部署 Exchange 2019 伺服器上的收件者信箱。 在判斷您的網際網路連線能力是否足以支援雲端語音信箱時，您需要將這種語音流量納入考慮。

以下是完成此遷移的高層級步驟。

1. 在新伺服器上安裝和設定商務用 Skype Server 2019。
2. 更新您的混合部署設定，以包含新的商務用 Skype 2019 server。
3. 在新伺服器上安裝和設定 Exchange Server 2019。
4. 將使用者從商務用 Skype 2015 伺服器移至商務用 Skype 2019 伺服器。
5. 將每個已移動至商務用 Skype Server 2019 的使用者的主控語音信箱原則，設定為使用雲端語音信箱。
6. 將信箱從您的 Exchange 2013 或 Exchange 2016 server 移至 Exchange 2019 伺服器。
7. 停用商務用 Skype 2015 伺服器後，最後一部使用者已移出這些伺服器。
8. 停用 Exchange 2013 或 Exchange 2016 伺服器後，最後一個信箱已經移出。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答，請至少保留一部 Exchange 2013，或 Exchange 2016 的執行和可用狀態。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>商務用 Skype Server 2015 至商務用 Skype Server 2019 搭配 Exchange 2013/Exchange 2016

在此案例中，您想要將現有的商務用 Skype 2015 伺服器遷移至商務用 Skype Server 2019，但仍然保留 Exchange 2013 或 Exchange 2016。

在相同的組織中商務用 Skype Server 2015 和商務用 Skype Server 2019 共存時，他們就能與 Exchange UM 和雲端語音信箱順利運作，以確保語音信箱已正確地傳遞至 Exchange 信箱。 Exchange UM 或雲端語音信箱是否會處理語音信箱，是否取決於使用者位於商務用 Skype Server 2015 或商務用 Skype Server 2019：

- 如果使用者位於商務用 Skype Server 2015 上，Exchange UM 會處理語音信箱訊息。
- 如果使用者位於商務用 Skype Server 2019 上，雲端語音信箱會處理語音信箱訊息。

不論 Exchange UM 或雲端語音信箱是否處理語音信箱訊息，郵件都會儲存在使用者的 Exchange 信箱中。

在您開始商務用 Skype Server 2019 的遷移之前，請記住下列事項：

- 雲端語音信箱不支援正式發行的組織自動語音應答。 如果您想要將信箱移至雲端語音信箱以繼續透過自動語音應答取得，您必須至少有一個 Exchange 2013 或 Exchange 2016 server 執行 UM 角色或服務。
- 傳送至語音信箱的來電會轉接至要記錄的雲端語音信箱。 通話結束後，語音信箱訊息會傳送至內部部署 Exchange server 上的收件者信箱。 在判斷您的網際網路連線能力是否足以支援雲端語音信箱時，您需要將這種語音流量納入考慮。

以下是完成此遷移的高層級步驟。

1. 在新伺服器上安裝和設定商務用 Skype Server 2019。
2. 更新您的混合部署設定，以包含新的商務用 Skype 2019 server。
3. 將使用者從商務用 Skype 2015 伺服器移至商務用 Skype 2019 伺服器。
4. 將每個已移動至商務用 Skype Server 2019 的使用者的主控語音信箱原則，設定為使用雲端語音信箱。
5. 停用商務用 Skype 2015 伺服器後，最後一部使用者已移出這些伺服器。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答，請至少保留一部 Exchange 2013，或 Exchange 2016 的執行和可用狀態。
