---
title: 針對內部部署使用者規劃雲端語音信箱服務 |PBX 商務用 Skype Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文說明實施 Microsoft 雲端語音信箱服務的優點、規劃考慮及需求。 如需設定雲端語音信箱的相關資訊, 請參閱設定雲端語音信箱。
ms.openlocfilehash: 0071154ab1b9c1211725dd9b6addc2dfd5449e15
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2019
ms.locfileid: "36185530"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>為內部部署使用者規劃雲端語音信箱服務

## <a name="overview"></a>概觀

本文說明針對您的內部部署使用者實施 Microsoft 雲端語音信箱服務的優點、規劃考慮及需求。 如需設定雲端語音信箱的相關資訊, 請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。

雲端語音信箱取代 Exchange 整合訊息 (UM), 提供在 Exchange Server 2019 或 Exchange Online 上擁有信箱之商務用 Skype 2019 語音使用者的語音訊息功能。 雲端語音信箱可為您的內部部署和線上使用者提供下列好處:

- 使用增強的語音對話來應答及放入功能的語音信箱

- 使用商務用 Skype Online 或 Outlook 用戶端, 在使用者的 Exchange 信箱中存取語音信箱

- 使用 Office 365 web 入口網站來管理語音信箱選項的能力

- 在內部部署或雲端的 Exchange 信箱支援

- 從 Exchange Online 整合通訊中使用現有的使用者問候語

如需功能比較的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。

商務用 Skype Server 2019 會繼續針對其信箱位於舊版 Exchange Server (2013、2016) 的使用者使用 Exchange UM。  瞭解將根據 Exchange Server 和商務用 Skype Server 版本使用哪些語音信箱方案, 是規劃遷移到商務用 Skype Server 2019 或 Exchange Server 2019 的重要部分。 如需有關移植與互通性的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。

使用雲端語音信箱, 您的管理工作會大大簡化, 因為:

- 您不需要設定 Exchange UM 角色。
- 雲端語音信箱的設定工作變得更簡單。
- 語音信箱功能的更新會直接在雲端傳送, 所以您的使用者永遠能夠存取最新功能和更新, 而不依賴累計更新 (CUs)。
- 您在內部部署和線上 Exchange 信箱中都有相同的控制項集合。 如需這些控制項的詳細資訊, 請參閱[設定電話系統語音信箱](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)。

下圖顯示混合式部署中的雲端語音信箱:

![SfB 雲端語音信箱](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

未接聽的通話處理方式如下:  

1. 針對駐留在商務用 Skype 2019 內部部署的使用者, 未回復的通話會由內部部署商務用 Skype 伺服器傳送給線上雲端語音信箱服務。
2. 此服務會處理語音信箱, 包括 [文字]。
3. 然後, 此服務會將語音信箱存款至使用者的 Exchange 信箱中, 不論該信箱是內部部署還是在線上。  
4. 使用者可以從商務用 Skype 或 Outlook 用戶端存取其語音信箱。

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype 伺服器。  您的需求取決於您的案例:

- 如果您已在線上使用 Exchange UM, 且您升級至商務用 Skype 2019, 您將需要修改託管的語音信箱原則, 並確認您的主機服務提供者已正確設定。 如需詳細資訊, 請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。

- 如果您是在內部部署使用 Exchange UM, 或是使用 Exchange UM online 和內部部署的使用者混合, 您將需要修改您的託管語音信箱原則和主機服務提供者。  如需詳細資訊, 請參閱[設定雲端語音信箱服務](configure-cloud-voicemail.md)。

- 針對雲端語音信箱的新設定, 請依照[設定雲端語音信箱服務](configure-cloud-voicemail.md)中所述的步驟進行。

除了上述需求之外, 下列需求必須設定為連線至 Microsoft 雲端語音信箱服務:

- 混合式連線性。 如果您已部署商務用 Skype Server, 且想要為您的內部部署使用者啟用雲端語音信箱, 您必須確保您在內部部署與線上環境之間已設定混合式連接。 這有時稱為分割網域配置。

   如需詳細資訊, 請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md), 以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

- 在商務用 Skype Server 中, 您必須在企業語音及託管語音信箱中啟用內部部署使用者。

- 必須設定外部 Exchange Web 服務 (EWS) URL 和自動探索, 或一些雲端語音信箱功能將會受到限制。

- 如果您僅限內部部署&#x2014;也就是, 只有 Exchange 和商務用 Skype 內部部署伺服器&#x2014;, 但是您想要利用雲端語音信箱, 就不需要額外的授權。

## <a name="migration-and-interoperability"></a>遷移和互通性

如果您打算部署商務用 Skype Server 2019 和/或 Exchange Server 2019, 您必須仔細規劃遷移, 以確保繼續提供語音訊息服務。 請記住下列事項:

- Exchange Server 2019 不再提供 Exchange UM 功能
- 商務用 Skype Server 2019 不再與 Exchange Online UM 整合

[雲端語音信箱] 的版本互通性和支援的拓撲會列在下表中, 此表格會比較使用者可能駐留的商務用 Skype 伺服器版本, 以及提供 Exchange 信箱的可能版本。 雲端語音信箱只適用于商務用 Skype Server 和 Exchange Server 2019 或 Exchange Online。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| 商務用 Skype Server 2019 | Exchange Server UM | Exchange Server UM | 雲端語音信箱 | 雲端語音信箱 |
| 商務用 Skype Server 2015 | Exchange Server UM | Exchange Server UM | 雲端語音信箱<sup>1</sup> | 雲端語音信箱 <br> Exchange Online UM<sup>2</sup> |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | 不支援 | 雲端語音信箱 <br> Exchange Online UM<sup>2</sup> |

<sup>1</sup>還沒有看到這個選項嗎？ 目前正在推出, 您的組織可能無法使用。 請參閱步驟 6, 考慮選擇 [ [Exchange 整合訊息] 線上遷移支援](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support
), 以加入與雲端語音信箱的計畫內連接。

<sup>2</sup> , 直到棄用為止。 如需詳細資訊, 請參閱[Exchange 整合訊息線上遷移支援](../../sfbserver2019/plan/exchange-unified-messaging-online-migration-support.md)。 

Microsoft 建議下列遷移路徑:

- 如果您要升級到商務用 Skype Server 2019, 您可以在 Exchange Server 2013 或2016中使用 Exchange UM, 但如果您使用的是 Exchange Server 2019, 則必須升級至雲端語音信箱。
- 如果您要升級到 Exchange Server 2019, 且您使用舊版 Exchange Server UM 進行商務用 Skype Server 語音訊息, Microsoft 建議您先升級到商務用 Skype Server 2019, 然後再升級信箱。  否則, 語音訊息功能將會遺失。
- 如果您要升級到商務用 Skype Server 2019, 且已針對含 Exchange Online UM 的語音信箱設定商務用 Skype Server 2015, 則使用者的語音信箱會自動從 Exchange Online UM 遷移到雲端語音信箱 (當他們的帳戶移至商務用 Skype Server 2019。 

如需規劃遷移的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。
