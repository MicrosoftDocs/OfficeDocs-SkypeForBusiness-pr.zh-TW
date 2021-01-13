---
title: 在商務用 Skype Server 2015 中規劃 Persistent Chat Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃 Persistent Chat Server。
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813663"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中規劃 Persistent Chat Server
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃 Persistent Chat Server。
  
Persistent Chat Server 是一種選用角色，可讓您組織中的多位使用者參與隨時間持續的聊天室交談。 雖然使用者可以在聊天會話中即時通訊，但每個會話的內容（包括文字、連結及檔案）都是持續性的，這表示使用者可以隨時查看及搜尋會話的所有內容。
  
Persistent Chat Server 可以協助改善組織內的通訊：
  
- 拓寬整個組織的資訊意識和參與
    
- 啟用有效的資訊共用 
    
- 改善小組之間的通訊，包括地理位置分散及跨職能團隊
    
- 減少資訊超載
    
- 依照選用方式部署 Persistent Chat 合規性服務，遵循相容性法規

> [!NOTE] 
> 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Persistent Chat Server 高層級架構

下圖顯示 Persistent Chat Server 架構的高層級視圖。 
  
![Persistent Chat Server 高層架構](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Persistent Chat 包含一種前端伺服器角色，可提供持久聊天服務及後端 SQL 資料庫元件。 前端和後端元件都包含在專用的持久聊天集區中。 主控 Persistent Chat Server 的每一部電腦都必須能夠存取現有的商務用 Skype Server 2015 拓撲。 在此圖中，有一個 Persistent Chat Server 集區 () ，該取決於商務用 Skype Server 集區 A，可將郵件路由傳送至該。
  
您可以部署一或多個 Persistent Chat Server 集區，每個集區最多可支援最多四個使用中80K 並行使用者的主動持久聊天伺服器。
  
商務用 Skype Server 2015 可使用會話初始通訊協定 (SIP) 進行登錄和透過 SIP 通訊協定 (XCCOS) 進行聊天，以與 Persistent 聊天服務進行通訊。 
  
## <a name="persistent-chat-services"></a>Persistent Chat service

下圖顯示 Persistent Chat Server 前端服務，以及這些服務如何與後端資料庫元件通訊。 前端元件包括持久聊天服務和規範服務。 後端元件包括 Persistent Chat store 和 Persistent Chat 規範存放區。
  
![Persistent Chat Server 高層服務](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>聊天室服務

聊天服務也稱為通道服務，是負責 Persistent Chat Server 的核心服務。 Chat service 提供下列功能：
  
- 接受傳入訊息
    
- 在持續聊天室內註冊和列出線上參與者
    
- 重新傳輸訊息給其他通道訂閱者
    
- 針對通道管理、聊天室邀請、搜尋及新內容通知的實施邏輯
    
Persistent Chat service 會透過使用 Persistent 聊天室存放區，儲存和存取聊天室內容及其他系統中繼資料 (授權規則等等) 。 該服務會將上傳至聊天室的檔案儲存在 Persistent Chat file store 中。
  
### <a name="compliance-service"></a>規範服務

如果貴組織的法規要求封存持續聊天活動，您可以部署選用的持續性聊天規範服務。 規範服務負責將聊天內容和事件（例如加入和離開會議室）封存到 Persistent Chat 規範檔案存放區。 規範服務是安裝在 Persistent Chat 集區中的每個 Persistent Chat Server 上。 
  
### <a name="web-services"></a>Web 服務

在商務用 Skype 前端伺服器上執行 Persistent Chat web 服務。 Web 服務取決於網際網路資訊服務 (IIS) ，並以 web 元件的形式來執行：
  
- 檔案上傳與下載的持續性聊天 web 服務負責電子檔上傳及從聊天室中檢索檔案。
    
- 聊天室管理的 Persistent Chat web 服務負責為使用者提供管理其聊天室的能力，以及建立新的聊天室。
    
## <a name="defining-requirements-for-your-organization"></a>定義組織的需求

如果您決定部署 Persistent Chat Server，則必須判斷組織的業務需求，然後定義拓撲、基礎結構和技術需求，以支援您的業務需求。 若要優化您的部署，您必須回答下列問題：
  
- 您是從舊版的群組聊天伺服器或舊版本的 Persistent Chat Server 進行遷移，還是第一次部署 Persistent Chat Server？
    
- 誰可以使用 Persistent Chat Server？ 您可以指定 Persistent 聊天原則，以決定全域、網站或使用者層級的使用者存取權。
    
- 需要有多少使用者才能存取 Persistent Chat Server？ Persistent Chat Server 支援150000布建使用者 (由原則) 啟用，且最多可有80000同時使用者。 單一 Persistent Chat Server 可以支援20000連線的使用者，而單一持久聊天伺服器集區最多可以有四個作用中的伺服器，共80000個同時連線的使用者。
    
- 您想要如何控制範圍、道德界限及存取？ 您可以定義類別以隔離這些界限，並選擇可在每個類別中建立的會議室。
    
- 您想要如何控制可以建立聊天室的人員？ 您可以定義可以建立聊天室的建立者。 建立者可以將其他成員指派為聊天室管理員，以進行持續的管理工作室。
    
- 您想要如何建立聊天室？ Persistent Chat Server 提供用來建立及管理聊天室的 web 型功能。 這可以從商務用 Skype 用戶端啟動。 您可以選擇定義客戶解決方案，以執行您的業務需求和工作流程，並設定 Persistent Chat Server 將使用者導向至您的自訂解決方案。
    
- 您想要佈建哪些種類的增益集？ 增益集利用商務用 Skype 用戶端中的擴充性窗格，以提供與會議室相關的內容，增強會議室的體驗。 您可以選擇哪些一般增益集最有用 (例如，貴公司的網站、內部共同作業元件等)。 聊天室管理員可以選擇其中一個登錄的增益集，並視需要將它關聯至他們的聊天室。 
    
- 您有哪些種類的高可用性與災害復原需求？ Persistent Chat Server 支援 SQL Server 鏡像和 SQL Server 叢集以取得高可用性。 針對嚴重損壞修復，Persistent Chat Server 最多可支援8部伺服器 (使用 SQL Server 記錄傳送的延伸集區中的4個作用中和4個待命) 。 
    
- 是否有法規需求？ 如果貴公司所在的國家或地區中的資料必須保留在全國，您可能需要將多個 Persistent 聊天伺服器集區，部署到特定地理位置的各個地方。 會議室、類別或增益集不會跨越集區，只隸屬于一個 Persistent Chat Server 集區。 
    
    > [!NOTE]
    > 具有多個 Persistent Chat Server 集區不會提供更多規模 (您仍然可以在所有持久聊天伺服器集區) 上僅有80000並行的使用者。 支援多個 Persistent Chat Server 集區的主要原因是支援法規考慮。 
  
## <a name="for-more-information"></a>相關資訊

如需安裝及設定 Persistent Chat Server 的詳細資訊，請參閱下列主題：
  
- 如需如何部署 Persistent Chat Server 的詳細資訊，請參閱 [Deploy Persistent Chat server In 商務用 Skype server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。 
    
- 如需如何設定持久聊天伺服器部署設定的詳細資訊，請參閱 [Manage Persistent Chat server In 商務用 Skype server 2015](../../manage/persistent-chat/persistent-chat.md)。
    

