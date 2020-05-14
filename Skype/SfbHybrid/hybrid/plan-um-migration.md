---
title: 規劃商務用 Skype Server 和 Exchange Server 遷移
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
description: 本主題涵蓋當您決定將現有的商務用 Skype 伺服器或 Exchange Server 部署遷移至最新版本或商務用 Skype Online 或 Exchange Online 時，需要考慮的事項。
ms.openlocfilehash: fec12eb5b386222ad0a69115ca3fc9e2de9e2fea
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221263"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>規劃商務用 Skype Server 和 Exchange Server 遷移

本主題涵蓋當您決定將現有的商務用 Skype 伺服器或 Exchange Server 部署遷移至最新版本或商務用 Skype Online 或 Exchange Online 時，需要考慮的事項。 您可以遷移的功能和時間取決於您已在組織中設定的專案。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和商務用 Skype Server 2019 中的功能變更

在 Exchange 2019 和商務用 Skype Server 2019 中，我們將對我們所支援的功能進行一些變更。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 中的整合通訊支援

整合通訊（UM）在 Exchange 2019 中已被取代。 這表示 Exchange 2019 不再提供下列功能：

- 語音信箱
- 自動語音應答

如果您已在 Exchange 2013 或 Exchange 2016 中的 UM 服務中部署 UM 角色，且您想升級為 Exchange 2019，您必須將語音信箱遷移至 Microsoft 雲端語音信箱服務的 Microsoft 365 或 Office 365。 如果您想要將語音信箱遷移至雲端語音信箱，請參閱以下的[exchange 2013/exchange 2016 和商務用 skype 2015 To exchange 2019 和商務用 skype 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)區段。
> [!IMPORTANT]
> 如果 Exchange 2013 或 Exchange 2016 伺服器上的使用者有已啟用 UM 的信箱，請不要將商務用 Skype 伺服器升級至 Exchange 2019，然後再將商務用 Skype 伺服器升級至商務用 Skype 伺服器2019，並將使用者移至這些伺服器以避免語音訊息中斷。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和商務用 Skype Server 2019 中的 PBX 支援

雲端語音信箱不會提供語音訊息功能到私人分支交換（PBXs）。 如果您要將 Exchange Server 整合通訊用於 PBXs，而您想升級至 Exchange Server 2019，您必須採用下列其中一項在博客文章中列出的選項，來終止[Exchange 小組博客](https://blogs.technet.microsoft.com/exchange/)上[Exchange Online 整合通訊中的會話邊界控制器的支援](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>商務用 Skype Server 2019 中的 Exchange Online UM 支援

使用商務用 Skype Server 2019，我們正在從 Exchange Online UM 移至雲端語音信箱。 當使用者移至商務用 Skype 2019 server 時，他們會在設定為主控語音信箱時，自動開始使用雲端語音信箱。 如果您目前使用的是 Exchange Online UM，除了將使用者移至商務用 Skype Server 2019 以外，您不需要執行任何動作，即可開始使用雲端語音信箱。 不過，您需要注意的功能有一些變更：

- 組織自動語音應答是 Exchange Online UM 中自動語音應答的取代。
- Outlook 網頁版中的使用者語音信箱設定不適用於雲端語音信箱。

## <a name="on-premises-um-migration-scenarios"></a>內部部署 UM 遷移案例

我們支援下列案例，可讓您將使用者遷移至 Exchange 2019 和雲端語音信箱。

- Exchange 2013/Exchange 2016 和商務用 Skype Server 2015 至 Exchange 2019 和商務用 Skype Server 2019
- 商務用 skype Server 2015 至商務用 Skype Server 2019，含 Exchange 2013/Exchange 2016

在下列情況下，您目前的部署中不會存在 PBX 或 SBC 設定，假設您已在內部部署 Exchange 伺服器上設定 UM。 這兩種方案也會假設您已決定在您的內部部署商務用 Skype 伺服器與 Microsoft 365 或 Office 365 之間設定混合式部署。 如需商務用 Skype 混合式部署的詳細資訊，請參閱[規劃混合](plan-hybrid-connectivity.md)式連線。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和商務用 Skype 2015 至 Exchange 2019 和商務用 Skype 2019

在此案例中，您想要將現有的 Exchange 2013、Exchange 2016 和商務用 Skype 2015 伺服器遷移至 Exchange 2019 和商務用 Skype 的2019。

如本主題稍早所述，Exchange 2019 不再包含 UM 服務。 這表示，針對您想要移至 Exchange 2019 的任何信箱，您必須使用雲端語音信箱來取代 UM 服務所提供的功能。 當您設定商務用 Skype Server 2019，以及其與 Microsoft 365 或 Office 365 之間的混合式部署時，雲端語音信箱會取代這些 Exchange UM 語音信箱服務。

您將使用者移至 Exchange 2019 和商務用 Skype Server 2019 的順序，對於確保所有使用者都能繼續使用語音信箱功能是很重要的。 使用語音信箱的處理方式，也取決於 Exchange 和商務用 Skype 信箱和使用者所在的位置。 請查看下表，以查看支援哪些 Exchange 和商務用 Skype Server 組合，以及處理語音信箱的位置。

| 信箱位於：            | 位於商務用 Skype Server 上的使用者2015 | 位於商務用 Skype Server 上的使用者2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支援                           | 雲端語音信箱                          |

開始遷移至商務用 Skype Server 2019 和 Exchange 2019 之前，請記住下列事項：

- 雲端語音信箱不支援正式發行的組織自動語音應答。 如果您想要將信箱移至雲端語音信箱以透過自動語音應答繼續提供，您必須至少有一個 Exchange 2013 或 Exchange 2016 伺服器執行 UM 角色或服務。
- 您必須先設定至少一部商務用 Skype 2019 server **，並**將使用者移至該伺服器，再將其信箱移至 Exchange 2019。 若失敗，將會導致這些信箱無法接收語音信箱訊息。
- 傳送至語音信箱的來電會轉接至雲端語音信箱，並在其中記錄。 通話結束後，語音信箱訊息會傳送至內部部署 Exchange 2019 伺服器上的收件者信箱。 在判斷您的網際網路連線能力是否足以支援雲端語音信箱時，您需要將這種語音流量納入考慮。

以下是完成此遷移的高層級步驟。

1. 在新的伺服器上安裝及設定商務用 Skype Server 2019。
2. 更新您的混合部署設定，以包含新的商務用 Skype 2019 server。
3. 在新伺服器上安裝和設定 Exchange Server 2019。
4. 將使用者從商務用 Skype 2015 server 移至商務用 Skype 2019 伺服器。
5. 針對移至商務用 Skype Server 2019 的每一位使用者，設定所主控的語音信箱原則，以使用雲端語音信箱。
6. 將信箱從 Exchange 2013 或 Exchange 2016 伺服器移至 Exchange 2019 伺服器。
7. 停用商務用 Skype 2015 伺服器後，最後一部使用者已移出這些伺服器。
8. 停用 Exchange 2013 或 Exchange 2016 伺服器後，最後一個信箱已經移出。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答，請至少保留一個 Exchange 2013 或 Exchange 2016 的執行和可用狀態。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>商務用 skype Server 2015 至商務用 Skype Server 2019，含 Exchange 2013/Exchange 2016

在此案例中，您想要將現有的商務用 Skype 2015 伺服器遷移至商務用 Skype Server 2019，但仍然保留在 Exchange 2013 或 Exchange 2016。

當商務用 Skype Server 2015 和商務用 Skype Server 2019 共存于相同組織時，他們可以與 Exchange UM 和雲端語音信箱順利運作，以確保語音信箱已正確地傳遞至 Exchange 信箱。 Exchange UM 或雲端語音信箱是否可以處理語音信箱，取決於使用者是否位於商務用 Skype Server 2015 或商務用 Skype Server 2019 上：

- 如果使用者位於商務用 Skype Server 2015，Exchange UM 將會處理語音信箱訊息。
- 如果使用者位於商務用 Skype Server 2019，雲端語音信箱會處理語音信箱訊息。

不論 Exchange UM 或雲端語音信箱是否處理語音訊息，郵件都會儲存在使用者的 Exchange 信箱中。

開始向商務用 Skype Server 2019 遷移之前，請記住下列事項：

- 雲端語音信箱不支援正式發行的組織自動語音應答。 如果您想要將信箱移至雲端語音信箱以透過自動語音應答繼續提供，您必須至少有一個 Exchange 2013 或 Exchange 2016 伺服器執行 UM 角色或服務。
- 傳送至語音信箱的來電會轉接至雲端語音信箱，並在其中記錄。 通話結束後，語音信箱訊息會傳送至內部部署 Exchange 伺服器上的收件者信箱。 在判斷您的網際網路連線能力是否足以支援雲端語音信箱時，您需要將這種語音流量納入考慮。

以下是完成此遷移的高層級步驟。

1. 在新的伺服器上安裝及設定商務用 Skype Server 2019。
2. 更新您的混合部署設定，以包含新的商務用 Skype 2019 server。
3. 將使用者從商務用 Skype 2015 server 移至商務用 Skype 2019 伺服器。
4. 針對移至商務用 Skype Server 2019 的每一位使用者，設定所主控的語音信箱原則，以使用雲端語音信箱。
5. 停用商務用 Skype 2015 伺服器後，最後一部使用者已移出這些伺服器。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答，請至少保留一個 Exchange 2013 或 Exchange 2016 的執行和可用狀態。
