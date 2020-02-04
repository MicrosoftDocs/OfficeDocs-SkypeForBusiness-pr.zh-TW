---
title: Lync Server 2013：定義常設聊天室伺服器需求
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
ms.openlocfilehash: a0e7482ab85b72168e990eaa97b2f79cb3665532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中定義組織的常設聊天室伺服器需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-15_

在您為貴組織部署持續聊天伺服器之前，請務必考慮下列重要問題，以優化您的部署：

  - 應該為永久聊天伺服器啟用誰（使用者設定檔）？ 永久聊天伺服器是由可在全域、網站、池或使用者層級設定的原則所啟用。

  - 應該為持續聊天伺服器啟用多少使用者（小數位數）？ Persistent 聊天伺服器支援150000預配的使用者（由原則啟用），以及最多可使用持續聊天伺服器80000的併發使用者數上限。 單一持久聊天伺服器可支援20000連線的使用者，且單一持續式聊天伺服器池最多可以有4個作用中的伺服器，共80000個同時連接的使用者。

  - 您是從舊版的群組聊天伺服器進行遷移，還是第一次部署持久聊天伺服器？

  - 是否有合規性需求？ 持續聊天伺服器支援合規性。 合規性服務會在持續聊天伺服器前端伺服器上執行 collocated，而不需要在前一個群組聊天伺服器部署中單獨的電腦。 合規性是選擇性的，如果已選取，則需要一個必須設定為儲存合規性資料和事件的合規性資料庫。 您也可以將配接器設定成從合規性資料庫中取得資料，並轉換成另一種格式（例如 XML 檔案或 Exchange 託管的存檔）。

  - 您要如何控制範圍、道德界限及存取權？ 您可以定義**類別**來隔離這些界限，並選擇每個類別中所能建立的人員在會議室中。

  - 您想要如何控制誰可以建立聊天室？ 您可以將 [**製作者**] 設定為適合您的類別，誰可以建立會議室。 根據類別所設定的**AllowedMembers/DeniedMembers**範圍，創意者可以將其他成員指派為聊天室**管理員**，以便持續管理會議室（新增或移除其他成員）。

  - 您想要如何建立聊天室？ 持續聊天伺服器提供在會議室建立與管理的網路功能。 這可以從 Lync 2013 用戶端啟動。 您可以選擇定義自訂解決方案（使用持續式聊天伺服器軟體發展工具組（SDK））來執行您的業務需求與工作流程，並設定持久聊天伺服器以將使用者引導至您的自訂方案。

  - 您想要提供哪種增益集？ **增益集**利用 Lync 2013 用戶端中的 [擴充性] 窗格來提供與聊天室相關的內容，以增強會議室體驗。 您可以選擇一般的增益集最實用（例如，您的公司網站、內部共同作業檔等等）。 聊天室管理員可以選擇其中一個已註冊的增益集，並視需要將其與聊天室產生關聯。

  - 您擁有哪種類型的高可用性和災害復原需求？ 持續性聊天伺服器支援 SQL Server 鏡像與 SQL Server 群集，以提供高可用性，且最多支援8台伺服器（4個作用及4個備用），以及適用于災害復原的 SQL Server 記錄傳送。

  - 是否有法規要求？ 如果您的公司所在的國家/地區中需要將資料保留在全國，您可能需要將多個持續聊天伺服器池部署到特定地理位置。 [會議室]、[類別] 或 [增益集] 不會跨越多個池，只屬於一個持續聊天伺服器池。 您可以管理每個持續聊天伺服器池的類別、增益集和會議室。 您可以將使用者設定為在一或多個池中使用類別 AllowedMembers 範圍或聊天室的成員資格，來存取會議室，視您設計類別的方式而定。
    
    <div>
    

    > [!IMPORTANT]  
    > 擁有多個持續聊天伺服器池並不能提供更多規模（您仍可以在所有持久聊天伺服器池中同時連接80000並行連線的使用者）。 支援多個持續聊天伺服器池的主要原因是要支援法規問題。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

