---
title: Lync Server 2013： 定義 Persistent Chat Server 的需求
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
ms.openlocfilehash: 4e6d796f3d06a9749cdccc86f59271a739eaa7e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>定義 Lync Server 2013 中的 [for Persistent Chat Server 貴組織的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-01-15_

為貴組織部署常設聊天室伺服器之前，請務必考量下列關鍵問題以最佳化您的部署：

  - 誰應 for Persistent Chat Server 啟用 （使用者設定檔）？ Persistent Chat Server 會啟用可以設定全域、 網站、 集區或使用者層級的原則。

  - 使用者人數 （擴充） 應啟用 for Persistent Chat Server？ Persistent Chat Server 支援 150000 佈建的使用者 （由原則啟用），並使用 Persistent Chat Server 80000 位並行使用者的最大值。 在單一的常設聊天室伺服器可支援 20000 已連線的使用者，並在單一常設聊天室伺服器集區可以有最多總共為 80000 位同時連線的使用者 4 作用中的伺服器。

  - 會從舊版的群組聊天伺服器，您移轉或第一次 deploying Persistent Chat Server？

  - 是否有規範需求？ Persistent Chat Server 支援合規性。 規範服務會執行組合常設聊天室伺服器前端伺服器上，而不是在不同的電腦上一個 Group Chat 伺服器部署中的需求。 規範是選用的，如果選擇，就需要有規範資料庫，且必須將該資料庫設定為儲存規範資料和事件。 若要設定規範資料庫的資料並將轉換成另一種格式 （例如 XML 檔或 Exchange 託管封存） 介面卡。

  - 您想要如何控制範圍、道德界限及存取？您可以定義 **[類別]** 來隔離這些界限，並選擇允許進入聊天室的人員，這些聊天室是建立於每個類別中。

  - 您想要如何控制可以建立聊天室的人員？您可以設定適用於類別的 **[建立者]**，讓這類人員可以建立聊天室。建立者可以根據類別所設定的 **[允許的成員/遭拒的成員]** 範圍，將其他成員指派為 **[聊天室管理員]**，以便持續不斷地管理聊天室 (新增或移除其他成員)。

  - 您想要如何建立聊天室？ Persistent Chat Server 提供的 web 式功能的會議室架設與管理。 這可以從 Lync 2013 用戶端啟動。 您可以選擇定義的自訂解決方案 （藉由使用常設聊天室伺服器軟體開發套件 (SDK)） 實作您的業務需求與工作流程，並會以引導使用者到您的自訂解決方案的常設聊天室伺服器設定。

  - 您想要佈建哪些種類的增益集？ **增益集**來加強室內體驗運用 Lync 2013 用戶端提供與會議室相關的內容中的 [擴充性] 窗格。 您可以選擇哪些一般增益集最有用 (例如，貴公司的網站、內部共同作業元件等)。 聊天室管理員可以選擇其中一個登錄的增益集，並視需要將它關聯至他們的聊天室。

  - 您有哪些種類的高可用性與災害復原需求？ Persistent Chat Server 支援 SQL Server 鏡像和 SQL Server 叢集的高可用性和支援最多 8 部伺服器 （4 個作用中且 4 待命） 中的延伸集區與 SQL Server 記錄傳送進行災害復原。

  - 是否有法規需求？ 如果貴公司是在其中的資料必須保持國家/地區內的國家/地區中，您可能需要將多個 Persistent Chat Server 集區，每個本機部署至特定的地理位置。 會議室、 類別或增益集未跨越集區-它屬於只有一個 Persistent Chat Server 集區。 您可以管理類別、 增益集和每個 Persistent Chat Server 集區的聊天室的設定。 使用者可以設定為具有存取權使用 AllowedMembers 範圍的類別或聊天室的成員資格範圍，根據您如何設計您類別的一個或多個集區中的會議室。
    
    <div>
    

    > [!IMPORTANT]  
    > 具有多個 Persistent Chat Server 集區並不會提供更大的範圍 （您可以跨所有 Persistent Chat Server 集區仍有只有 80000 位同時連線的使用者）。 支援多個 Persistent Chat Server 集區的主要原因是要支援法規考量。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

