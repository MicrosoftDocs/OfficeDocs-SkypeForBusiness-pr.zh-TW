---
title: 規劃商務用 Skype Server 與 Exchange Server 遷移
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: 本主題涵蓋您決定要將現有的商務用 Skype 伺服器或 Exchange Server 部署遷移至最新版本或商務用 Skype Online 或 Exchange Online 時所需考慮的事項。
ms.openlocfilehash: b1e7f52da2f036ebf88b4a8986650bfbc20c38b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "36185428"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>規劃商務用 Skype Server 與 Exchange Server 遷移

本主題涵蓋您決定要將現有的商務用 Skype 伺服器或 Exchange Server 部署遷移至最新版本或商務用 Skype Online 或 Exchange Online 時所需考慮的事項。 您可以遷移的內容和時間, 主要取決於您在組織中已設定的專案。 某些功能 (例如組織自動語音應答) 不會在正式供貨 (GA) 中提供, 但稍後會在2018中推出。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和商務用 Skype Server 2019 中的功能變更

在 Exchange 2019 和商務用 Skype Server 2019 中, 我們會針對我們所支援的功能進行一些變更。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 中的整合訊息支援

Exchange 2019 中已棄用整合通訊 (UM)。 這表示 Exchange 2019 不再提供下列功能:

- 語音信箱
- 自動語音應答

如果您已在 Exchange 2013 或 Exchange 2016 中的 UM 服務中部署 UM 角色, 且想要升級到 Exchange 2019, 您必須將語音信箱遷移至 Office 365 中的 Microsoft 雲端語音信箱服務。 如果您想要將您的語音信箱遷移至雲端語音信箱, 請參閱下方的[exchange 2013/exchange 2016 和商務用 skype 2015 至 exchange 2019 和商務用 skype 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)區段。
> [!IMPORTANT]
> 如果您的 Exchange 2013 或 Exchange 2016 伺服器上的使用者具有 UM 啟用的信箱, 請不要將商務用 Skype 伺服器升級為 Exchange 2019, 然後再將使用者移至商務用 Skype Server 2019, 然後將使用者移至其中以避免語音資訊中斷。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 和商務用 Skype Server 2019 中的 PBX 支援

雲端語音信箱不會提供語音訊息功能給私人分支交換 (Pbx)。 如果您使用的是針對 Pbx 的 Exchange Server 整合訊息, 而您想要升級到 Exchange Server 2019, 您必須採用在博客文章新日期中所列的三個選項之一, 以[終止 Exchange 中的會話邊界控制器支援](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) [Exchange 小組博客](https://blogs.technet.microsoft.com/exchange/)上的線上整合訊息。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>商務用 Skype Server 2019 中的 Exchange Online UM 支援

透過商務用 Skype Server 2019, 我們正從 Exchange Online UM 移至雲端語音信箱。 當使用者移至商務用 Skype 2019 伺服器時, 系統會在針對託管語音信箱設定的情況下, 自動開始使用雲端語音信箱。 如果您目前使用的是 Exchange Online UM, 除了將使用者移至商務用 Skype Server 2019 之外, 您不需要執行任何其他動作, 即可開始使用雲端語音信箱。 不過, 您需要注意的功能有一些變更:

- 組織自動語音應答 (Exchange Online UM 中的自動回應取代) 無法在正式提供, 但稍後會在2018中提供。
- Outlook 網頁版中的使用者語音信箱設定不適用於雲端語音信箱。

## <a name="on-premises-um-migration-scenarios"></a>內部部署 UM 遷移案例

我們支援下列案例, 可讓您將使用者同時遷移至 Exchange 2019 和雲端語音信箱。 在稍後的2018中, 我們將會支援其他案例, 讓您從其他版本的 Exchange 和商務用 Skype server 進行遷移。 我們也會提供其他功能, 例如組織自動語音應答。

- Exchange 2013/Exchange 2016 和商務用 Skype Server 2015 至 Exchange 2019 和商務用 Skype Server 2019
- 使用 Exchange 2013/Exchange 2016 的商務用 skype Server 2015 至商務用 Skype Server 2019

下列案例要求在您的內部部署 Exchange 伺服器上, 不會存在任何 PBX 或 SBC 設定, 並假設您已在內部部署 Exchange 伺服器上設定 UM。 這些解決方案中的每一個都假設您已決定在您的內部部署商務用 Skype 伺服器與 Office 365 之間設定混合式部署。 如需商務用 Skype 混合式部署的詳細資訊, 請參閱[規劃混合式連線性](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 和商務用 Skype 2015 至 Exchange 2019 和商務用 Skype 2019

在這種情況下, 您想要將現有的 Exchange 2013、Exchange 2016 及商務用 Skype 2015 伺服器遷移至 Exchange 2019 和商務用 Skype 2019。

如本主題先前所述, Exchange 2019 不再包含 UM 服務。 這表示, 對於您想要移至 Exchange 2019 的任何信箱, 您必須使用雲端語音信箱來取代 UM 服務提供的功能。 當您設定商務用 Skype Server 2019 以及 it 與 Office 365 之間的混合式部署時, 雲端語音信箱會取代這些 Exchange UM 語音信箱服務。

您將使用者移至 Exchange 2019 和商務用 Skype Server 2019 的順序, 對於確保所有使用者都能使用語音信箱功能是至關重要的。 處理語音信箱的位置也是由 Exchange 和商務用 Skype 信箱和使用者所在的位置決定。 請參閱下表, 查看支援哪些 Exchange 和商務用 Skype Server 組合, 以及處理語音信箱的位置。

| 信箱位於:            | 位於商務用 Skype Server 2015 的使用者 | 位於商務用 Skype Server 2019 的使用者  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 不支援                           | 雲端語音信箱                          |

開始遷移到商務用 Skype Server 2019 和 Exchange 2019 之前, 請記住下列事項:

- 雲端語音信箱不支援在 GA 正式提供組織自動語音應答。 如果您想要透過自動語音應答將信箱移至雲端語音信箱, 您必須至少有一個 Exchange 2013 或 Exchange 2016 伺服器執行 UM 角色或服務。
- 您必須先設定至少一個商務用 Skype 2019 伺服器 **, 並**將使用者移至該伺服器, 才能將其信箱移至 Exchange 2019。 如果不這麼做, 將會導致這些信箱無法接收語音信箱訊息。
- 傳送給語音信箱的通話會傳送到雲端語音信箱, 並記錄在其中。 通話結束之後, 語音信箱訊息就會傳送到內部部署 Exchange 2019 伺服器上的收件者信箱。 在判斷您的網際網路連線是否足以支援雲端語音信箱時, 您必須將此語音流量納入考慮。

以下是完成這種遷移的最高層步驟。

1. 在新的伺服器上安裝並設定商務用 Skype Server 2019。
2. 更新您的混合式部署配置, 以包含新的商務用 Skype 2019 伺服器。
3. 在新伺服器上安裝並設定 Exchange Server 2019。
4. 將使用者從商務用 Skype 2015 伺服器移至商務用 Skype 2019 伺服器。
5. 針對移至商務用 Skype Server 2019 的每個使用者, 將 [託管語音信箱原則] 設定為使用雲端語音信箱。
6. 將信箱從 Exchange 2013 或 Exchange 2016 伺服器移至 Exchange 2019 伺服器。
7. 當您的商務用 Skype 2015 伺服器停用之後, 請解除授權。
8. 在移動完最後一個信箱之後, 請解除 Exchange 2013 或 Exchange 2016 伺服器。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答, 請至少保留一個 Exchange 2013 或 Exchange 2016, 且可供使用。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>使用 Exchange 2013/Exchange 2016 的商務用 skype Server 2015 至商務用 Skype Server 2019

在這種情況下, 您想要將現有的商務用 Skype 2015 伺服器遷移到商務用 Skype Server 2019, 但仍會保留在 Exchange 2013 或 Exchange 2016 中。

當商務用 Skype Server 2015 與商務用 Skype Server 2019 在同一個組織中共存時, 它們會與 Exchange UM 和雲端語音信箱完美搭配, 以確保語音正確傳送至 Exchange 信箱。 Exchange UM 或雲端語音信箱是否會處理語音信箱, 取決於使用者是否位於商務用 Skype Server 2015 或商務用 Skype Server 2019:

- 如果使用者位於商務用 Skype Server 2015 上, Exchange UM 會處理語音信箱訊息。
- 如果使用者位於商務用 Skype Server 2019 上, 雲端語音信箱會處理語音信箱訊息。

無論 Exchange UM 或雲端語音信箱處理語音信箱訊息, 郵件都會儲存在使用者的 Exchange 信箱中。

開始遷移到商務用 Skype Server 2019 之前, 請記住下列事項:

- 雲端語音信箱不支援在 GA 正式提供組織自動語音應答。 如果您想要透過自動語音應答將信箱移至雲端語音信箱, 您必須至少有一個 Exchange 2013 或 Exchange 2016 伺服器執行 UM 角色或服務。
- 傳送給語音信箱的通話會傳送到雲端語音信箱, 並記錄在其中。 通話結束之後, 語音信箱訊息就會傳送到內部部署 Exchange 伺服器上的收件者信箱。 在判斷您的網際網路連線是否足以支援雲端語音信箱時, 您必須將此語音流量納入考慮。

以下是完成這種遷移的最高層步驟。

1. 在新的伺服器上安裝並設定商務用 Skype Server 2019。
2. 更新您的混合式部署配置, 以包含新的商務用 Skype 2019 伺服器。
3. 將使用者從商務用 Skype 2015 伺服器移至商務用 Skype 2019 伺服器。
4. 針對移至商務用 Skype Server 2019 的每個使用者, 將 [託管語音信箱原則] 設定為使用雲端語音信箱。
5. 當您的商務用 Skype 2015 伺服器停用之後, 請解除授權。

    > [!IMPORTANT]
    > 如果您依賴自動語音應答, 請至少保留一個 Exchange 2013 或 Exchange 2016, 且可供使用。
