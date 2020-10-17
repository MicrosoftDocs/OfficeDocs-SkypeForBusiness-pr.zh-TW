---
title: Lync Server 2013：定義 Persistent Chat Server 的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63e7af0dca758f6ac543bb0373d2cbb0d953ba0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504300"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中定義組織對 Persistent Chat Server 的需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-15_

在您為組織部署 Persistent Chat Server 之前，請務必考慮下列主要問題，以優化您的部署：

  - 應為 Persistent Chat Server 啟用 (使用者設定檔) 的使用者？ Persistent Chat Server 是由可以在全域、網站、集區或使用者層級設定的原則所啟用。

  - 應為 Persistent Chat Server 啟用 (比例) 的使用者人數？ Persistent Chat Server 支援150000布建使用者 (由原則) 啟用，且最多可使用持久聊天伺服器的80000併發使用者。 單一 Persistent Chat Server 可以支援20000連線的使用者，而單一持久聊天伺服器集區最多可以有四個作用中的伺服器，共80000個同時連線的使用者。

  - 您是從舊版的群組聊天伺服器進行遷移，還是第一次部署 Persistent Chat Server？

  - 是否有規範需求？ Persistent Chat Server 支援規範。 規範服務會在 Persistent Chat Server 前端伺服器上執行組合，而不是在先前的群組聊天伺服器部署中執行個別電腦的需求。 規範是選用的，如果選擇，就需要有規範資料庫，且必須將該資料庫設定為儲存規範資料和事件。 您也可以設定配接器，以取得規範資料庫中的資料，並轉換成其他格式 (例如 XML 檔案或 Exchange 主控的封存) 。

  - 您想要如何控制範圍、道德界限及存取？您可以定義 **[類別]** 來隔離這些界限，並選擇允許進入聊天室的人員，這些聊天室是建立於每個類別中。

  - 您想要如何控制可以建立聊天室的人員？您可以設定適用於類別的 **[建立者]**，讓這類人員可以建立聊天室。建立者可以根據類別所設定的 **[允許的成員/遭拒的成員]** 範圍，將其他成員指派為 **[聊天室管理員]**，以便持續不斷地管理聊天室 (新增或移除其他成員)。

  - 您想要如何建立聊天室？ Persistent Chat Server 提供以 web 為基礎的功能，用於建立及管理會議室。 這可以從 Lync 2013 用戶端啟動。 您可以選擇使用 Persistent Chat Server 軟體發展套件 (SDK) # A3 來定義自訂的方案 (，以執行您的業務需求和工作流程，並設定 Persistent Chat Server 將使用者導向至您的自訂解決方案。

  - 您想要佈建哪些種類的增益集？ **增益集** 利用 Lync 2013 用戶端中的「擴充性窗格，以提供與會議室相關的內容，增強會議室的體驗。 您可以選擇哪些一般增益集最有用 (例如，貴公司的網站、內部共同作業元件等)。 聊天室管理員可以選擇其中一個登錄的增益集，並視需要將它關聯至他們的聊天室。

  - 您有哪些種類的高可用性與災害復原需求？ Persistent Chat Server 支援 SQL Server 鏡像和 SQL Server 叢集的高可用性，並最多支援8部伺服器 (4 個作用中和4個待命) 在具有 SQL Server 記錄傳送的延伸集區中，以進行嚴重損壞修復。

  - 是否有法規需求？ 如果貴公司所在的國家/地區中的資料必須保留在國家/地區內，您可能需要將多個 Persistent Chat Server 集區，部署到特定地理位置的各個地方。 會議室、類別或增益集不會跨越集區，只屬於一個 Persistent Chat Server 集區。 您可以管理每個 Persistent Chat Server 集區的類別、增益集及會議室。 您可以設定使用者使用類別 AllowedMembers 範圍或會議室的成員資格範圍來存取一或多個集區中的聊天室，視您設計類別的方式而定。
    
    <div>
    

    > [!IMPORTANT]  
    > 具有多個 Persistent Chat Server 集區不會提供更多規模 (您仍然可以在所有持久聊天伺服器集區) 上，只讓80000並行連線的使用者。 支援多個 Persistent Chat Server 集區的主要原因是支援法規考慮。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

