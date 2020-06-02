---
title: 規劃內部部署使用者的雲端語音信箱服務 |PBX 商務用 Skype Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文說明實施 Microsoft Cloud 語音信箱服務的優點、規劃考慮和需求。 如需設定雲端語音信箱的詳細資訊，請參閱設定雲端語音信箱。
ms.openlocfilehash: b78608f3fd1e60421ad0edc4318b2b44217851c2
ms.sourcegitcommit: bdafa1f4146e615d325e27a50352f10c0d51ef1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2020
ms.locfileid: "44472252"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>規劃內部部署使用者的雲端語音信箱服務

## <a name="overview"></a>概觀

本文說明為您的內部部署使用者實施 Microsoft Cloud 語音信箱服務的優點、規劃考慮和需求。 如需設定雲端語音信箱的詳細資訊，請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。

雲端語音信箱會取代 Exchange 整合通訊（UM），以提供語音訊息功能，以供在 Exchange Server 2019 或 Exchange Online 上擁有信箱的商務用 Skype 2019 語音使用者使用。 雲端語音信箱為您的內部部署和線上使用者提供下列好處：

- 帶有增強語音功能的語音信箱應答和放入功能

- 使用商務用 Skype Online 或 Outlook 用戶端，存取使用者的 Exchange 信箱中的語音信箱

- 使用 Microsoft 365 系統管理中心管理語音信箱選項的功能

- 支援內部部署或雲端的 Exchange 信箱

- 從 Exchange Online 整合通訊利用現有的使用者問候語

如需有關功能比較的詳細資訊，請參閱[Plan For 商務用 Skype server 和 Exchange Server 遷移](plan-um-migration.md)。

商務用 Skype Server 2019 針對信箱在舊版 Exchange Server 上的使用者，繼續使用 Exchange UM （2013、2016）。  瞭解將根據 Exchange Server 和商務用 Skype Server 版本使用哪些語音信箱解決方案，是規劃將遷移至商務用 Skype Server 2019 或 Exchange Server 2019 的重要部分。 如需有關遷移和互通性的詳細資訊，請參閱[Plan For 商務用 Skype server 和 Exchange Server 遷移](plan-um-migration.md)。

透過雲端語音信箱，您的系統管理工作會極大地簡化，原因如下：

- 不需要設定 Exchange UM 角色。
- 雲端語音信箱的設定工作變得更簡單。
- 語音信箱功能的更新是直接在雲端中傳遞，所以您的使用者永遠可以存取最新的功能和更新，但不依賴累計更新（Cu）。
- 您可以在內部部署和線上 Exchange 信箱中使用相同的控制項集合。 如需這些控制項的詳細資訊，請參閱[Set Up Phone 系統語音信箱](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。

下圖顯示混合式部署中的雲端語音信箱：

![SfB 雲端語音信箱](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

未回復的呼叫的處理方式如下：  

1. 若為位於內部部署商務用 Skype 2019 的使用者，則內部部署商務用 Skype Server 會將未應答的呼叫傳送至線上雲端語音信箱服務。
2. 此服務會處理語音信箱，包括語音語音。
3. 然後，此服務會將語音信箱存款至使用者的 Exchange 信箱中，不論該信箱是內部部署或線上。  
4. 使用者可以從商務用 Skype 或 Outlook 用戶端存取其語音信箱。

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server。  您的需求取決於您的案例：

- 如果您已經在使用 Exchange UM 線上，且升級至商務用 Skype 2019，您將需要修改主控的語音信箱原則，並確認您的主機服務提供者設定正確。 如需詳細資訊，請參閱[Configure Cloud 語音信箱服務](configure-cloud-voicemail.md)。

- 如果您在內部部署上使用 Exchange UM，或是使用 Exchange UM online 和內部部署混合使用使用者，您就需要修改所裝載的語音信箱原則及主機服務提供者。  如需詳細資訊，請參閱[Configure Cloud 語音信箱服務](configure-cloud-voicemail.md)。

- 若要取得雲端語音信箱的新設定，請遵循[設定雲端語音信箱服務](configure-cloud-voicemail.md)中所述的步驟。

除了上述需求之外，還必須設定下列需求，才能連線至 Microsoft 雲端語音信箱服務：

- 混合連接。 如果您已部署商務用 Skype Server，而且想要為您的內部部署使用者啟用雲端語音信箱，您必須確定您的內部部署與線上環境之間已設定混合式連線能力。 這有時稱為分割網域設定。

   如需詳細資訊，請參閱[規劃商務用 Skype server 與 Microsoft 365 或 office 365 之間的混合](plan-hybrid-connectivity.md)式連線，以及[設定商務用 Skype server 與 office 365 的混合](configure-hybrid-connectivity.md)式連線。

- 內部部署使用者必須在商務用 Skype Server 中啟用 Enterprise Voice 和主控語音信箱。

- 必須設定外部 Exchange Web 服務（EWS） URL 和自動探索，否則將會限制部分雲端語音信箱功能。

- 如果您有內部部署 Exchange 伺服器，請使用[設定 Exchange Server 信箱使用者的雲端語音信箱](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)中的步驟，來設定雲端語音信箱。

## <a name="migration-and-interoperability"></a>遷移和互通性

如果您計畫要部署商務用 Skype Server 2019 和/或 Exchange Server 2019，您必須仔細規劃遷移，以確保持續的語音訊息服務。 請記住下列事項：

- Exchange Server 2019 不再提供 Exchange UM 功能
- 商務用 Skype Server 2019 不再與 Exchange Online UM 整合

下表列出雲端語音信箱的版本互通性和支援的拓撲，這會比較使用者可能所在的商務用 Skype Server 版本，其可提供其 Exchange 信箱的可能版本。 如果您想要使用商務用 Skype 2019 與 Exchange Online 或 Exchange Server 2019，您必須使用雲端語音信箱。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| 商務用 Skype Server 2019 | Exchange Server UM | Exchange Server UM | 雲端語音信箱 | 雲端語音信箱 |
| 商務用 Skype Server 2015 | Exchange Server UM | Exchange Server UM | 雲端語音信箱 | 雲端語音信箱 |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 不支援 | 雲端語音信箱 |

Microsoft 建議下列遷移路徑：

- 如果您要升級至商務用 Skype Server 2019，您可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果您使用 Exchange Server 2019，則必須升級至雲端語音信箱。
- 如果您要升級至 Exchange Server 2019，而您使用舊版的 Exchange Server UM 來進行商務用 Skype Server 語音訊息，Microsoft 建議您在信箱升級之前，先升級至商務用 Skype Server 2019。  否則，語音訊息功能將會遺失。
- 如果您要升級至商務用 Skype Server 2019，並已針對含 Exchange Online UM 的語音信箱設定商務用 Skype Server 2015，使用者的語音信箱將會在其帳戶移至商務用 Skype Server 2019 時，自動從 Exchange Online UM 遷移至雲端語音信箱。 

如需規劃遷移的詳細資訊，請參閱[規劃商務用 Skype Server 和 Exchange Server 遷移](plan-um-migration.md)。
