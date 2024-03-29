---
title: 功能概述規劃工具
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Descripbes 商務用 Skype Server 2015 規劃工具。
ms.openlocfilehash: 064ad9e22c3e4e26187b780b8d099a675bebc426
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386511"
---
# <a name="feature-overview-planning-tool"></a>功能概述規劃工具
 
商務用 Skype Server 2015 規劃工具
  
您可以使用規劃工具的「**中央網站**」頁面來設計商務用 Skype Server 部署。 您可以建立兩種集中式或分散式部署。 集中式部署只有一個中央網站，可讓您組織中的所有商務用 Skype 使用者。 分散式部署有一個以上的中央網站。 如果您在多部中央網站上部署商務用 Skype Server，您會在規劃工具中的每個中央網站上輸入使用者數目。
  
若要完成中央網站的定義，您必須先提供下列資訊：
  
- **網站名稱** 輸入中央網站的名稱。
    
- **使用者數目** 輸入使用者數目（包括位於中央網站的分支網站使用者）。
    
- **雲端穴使用者** 從商務用 Skype Online 中輸入位於中央網站的使用者數目。
    
> [!NOTE]
> 將不會更新商務用 Skype Server 2019 的此工具。

## <a name="ui-elements"></a>UI 元素

其餘的元素已填入您在 **入門** 嚮導中所提供的問題的答案，或者，如果您略過該嚮導，則會由規劃工具自動填入。
  
### <a name="online-collaboration"></a>線上合作

 **線上合作** 包含下列選項：
  
- **IM 和目前狀態**
    
    立即訊息 (IM) 可讓使用者在其電腦上使用文字型郵件進行即時通訊。 同時支援雙方或多方 IM 工作階段。 目前狀態為使用者提供有關網路上其他人狀態的資訊。 使用者的目前狀態會提供資訊，以協助其他人決定使用者是否線上，以及如何最好地聯繫使用者。 例如，在會議中的使用者最好是透過電子郵件聯繫。
    
- **音訊與視訊會議**
    
    Audio/Video (A/V) 會議可啟用即時音訊和視訊會議。
    
- **電話撥入式會議**
    
    電話撥入式會議可讓使用者從 PSTN 上的電話加入 A/V。 電話撥入式會議需要您部署會議語音應答和會議宣告服務應用程式。
    
- **Web 會議**
    
    Web 會議可讓防火牆內外的企業使用者建立及加入內部伺服器所主控的即時會議。
    
- **常設聊天室**
    
    Persistent Chat 可讓多位使用者參與交談，以在其中張貼和存取特定主題的內容，包括文字、連結及檔案。 雖然使用者可以在會話中即時進行通訊，但每個會話的內容都是持續性的，這表示當會話結束後，它仍可繼續使用。
    
### <a name="users"></a>使用者

 **使用者** 包含下列選項：
  
- **內部組織**
    
- **與其他組織同盟**
    
- **與舊版本的同盟**
    
- **與公用 IM 服務提供者的同盟** 可讓您組織中的使用者與公用立即訊息服務提供者（例如 MSN、Yahoo！和 AOL）建立通訊。 需要有個別的授權，才能建立與公用立即訊息網路的同盟。
    
- **與 XMPP 基礎服務提供者的同盟**
    
    商務用 Skype Server 2015 引進 (部署在 Edge server 上的完整整合式 XMPP proxy，) 和您的前端伺服器上部署的 XMPP 閘道。 您可以部署新增及設定 XMPP proxy 和 XMPP 閘道，讓商務用 Skype Server 2015 使用者從 XMPP 的協力廠商夥伴新增連絡人，以進行立即訊息 (IM) 和顯示狀態。

> [!NOTE]
> XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。
    
- **行動性**
    
    當您部署商務用 Skype Server 2015 行動性服務時，使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行這類活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。
    
- **W15 Exchange 信箱**
    
    商務用 Skype Server 2015 可讓您將語音信箱訊息儲存在 Exchange 整合通訊 (UM) 中; 這些語音信箱郵件會在使用者的收件匣中以電子郵件形式顯示。
    
### <a name="voice"></a>語音

 **Voice** 包含下列選項：
  
- **企業語音**
    
    Enterprise voice 是 Microsft 的軟體動力 VoIP 解決方案。 Enterprise 語音可讓使用者使用商務用 Skype 撥打來自其電腦的電話。
    
- **Exchange 整合通訊**
    
    Exchange 整合通訊 (UM) 將語音信箱和電子郵件結合成單一郵件基礎結構。 商務用 Skype Server 2015 使用 Exchange UM 來提供呼叫回應、使用者存取、來電通知和自動語音應答服務。 如果您使用這些服務，您將需要在共用 Active Directory 拓撲中整合 Exchange UM 和商務用 Skype Server。
    
### <a name="additional-deployment-options"></a>其他部署選項

 **其他部署選項** 包含下列選項：
  
- **高可用性**
    
    高可用性啟用容錯移轉支援的待機伺服器。
    
- **嚴重損壞修復**
    
    嚴重損壞修復措施可讓您將位於兩部資料中心的前端集區配對。
    
- **監視**
    
    監控會捕獲與通訊會話相關的詳細通話記錄。 此外，它也會從出席者端點的音訊和影片收集計量。 監控伺服器提供使用統計資料、趨勢及媒體質量統計資料。
    
- **封存**
    
    封存會儲存立即訊息交談和會議。
    
- **Exchange 封存整合**
    
    如果您有位於 Exchange 2013 的使用者，且其信箱已放在 In-Place 保留狀態，您可以選取此選項，以將商務用 Skype Server 2015 儲存區與 Exchange 儲存體整合。
    
- **IPv4**
    
    IPv4 位址是 32 位元位址，可讓電腦透過網際網路進行通訊。 由於世界各地的裝置數目不斷增加，所以可用的 IPv4 位址已用盡。因此，許多新裝置會移至使用 IPv6 位址。
    
- **IPv6**
    
    IPv6 位址執行與 IPv4 位址相同的功能 (並增加一些功能)，但是 IPv6 位址使用 128 位元，而不是只使用 32 位元。 這不僅提供全新的一組位址，也提供更多的位址數目。
    
- **裝置更新 Web 服務**
    
    裝置更新 Web 服務提供一種自動化的方式，可更新組織外部署的所有裝置，例如 Windows Phone 版商務用 Skype。
    
### <a name="server-applications"></a>伺服器應用程式

 **伺服器應用程式** 包含下列選項：
  
- **回應群組**
    
    回應群組應用程式會自動接聽並將通話分配給可用的服務台代理商。
    
- **公告**
    
    如果您打算部署企業語音，您可能想要在撥打的號碼有效但未指派給使用者共同區域時，設定處理電話的方式。 管理員可以設定宣告服務，讓這些來電轉接至預先決定的目的地 (電話號碼或 SIP URI) 或播放音訊宣告或兩者。 使用宣告服務可避免來電者 misdials 及聽到忙碌色調或 SIP 用戶端收到錯誤訊息的情況。 宣告服務功能是一般的 PBX 功能。 
    
- **通話駐留**
    
    通話駐留應用程式可讓企業語音使用者從一部電話接聽來電，然後從另一部電話接聽來電，而不會在接收通話的電話上撥打資源。 當使用者需要轉接通話，但特定收件者未知時，通話駐留應用程式十分有用。 
    
- **會議助理**
    
    會議語音應答應用程式會在不使用協力廠商音訊會議提供者的服務的情況下，為電話使用者提供音訊會議功能。
    
- **會議宣告**
    
    會議宣告應用程式會產生色調，當使用者進入或離開會議時，以及當電話使用者已靜音或 unmuted 時發出通知。
    
- **通話許可控制**
    
    通話許可控制 (CAC) （也稱為 WAN 頻寬管理）可協助您根據可用的頻寬，判斷是否允許及建立新的即時通訊會話，以防止使用者在擁擠的網路上的經驗品質不良。 
    
    > [!NOTE]
    > CAC 只會控制即時流量，而且不會影響資料流量。 
  
    如果新的語音或影片會話超過您在 WAN 上所指派的頻寬限制，則會話會封鎖或 (僅限通話) 重新路由至 PSTN。
    

