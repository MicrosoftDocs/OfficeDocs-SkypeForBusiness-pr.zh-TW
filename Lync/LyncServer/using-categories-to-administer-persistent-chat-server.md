---
title: 使用類別管理 Persistent Chat Server
description: 使用類別來管理 Persistent Chat Server。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ecba944a042e3598b2964ad233590cf63349e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579539"
---
# <a name="using-categories-to-administer-persistent-chat-server"></a>使用類別管理 Persistent Chat Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-01_

您的持久聊天伺服器部署可以主控許多併發的持久聊天室。 聊天室可以在伺服器上組織成一組類別。 每個聊天室各屬於一個類別，並繼承該類別的某些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。

<div>


> [!NOTE]  
> 雖然聊天室的許多管理功能均可在執行 Persistent Chat (Lync 用戶端) 的電腦上使用，但在 <STRONG>cspersistentchatadministrator</STRONG> role 中) 的持續性聊天系統管理員 (，必須使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立或管理類別。



</div>

Persistent Chat administrator 使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別，以及為組織中的使用者設計聊天室的存取。

Persistent 聊天室管理員（能夠管理一或多個聊天室）可以使用 Lync 用戶端來啟動聊天室管理 Web 應用程式，以建立及管理會議室 (或客戶可以建立自訂的解決方案和工作流程以) 進行呼叫。 Persistent Chat 系統管理員也可以使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理聊天室。

<div>


> [!NOTE]  
> Persistent 聊天室的名稱不能與 Persistent 聊天類別相同。



</div>

聊天室管理員可以變更所有的聊天室內容，但不能變更聊天室的類別。不能限制聊天室管理員執行下列動作：

  - 停用聊天室

  - 變更聊天室名稱

  - 變更聊天室說明

  - 變更聊天室類型 (視聽形式或是一般形式)

  - 變更聊天室的隱私權 (開放、關閉或秘密)

  - 新增或移除成員

  - 新增或移除聊天室管理員

  - 新增或移除增益集

  - 變更邀請等設定 (根據類別允許的內容)

<div>

## <a name="delegated-administration"></a>委派管理

正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。 Persistent Chat 管理員可以定義每個類別的 **AllowedMembers** 和建立 **者** ，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。 Persistent Chat 系統管理員可以使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別。

使用者、組織單位 (Ou) ，以及識別為類別建立者的使用者群組，都是唯一可以在類別中建立聊天室的個人和群組。 在建立類別之後，他們可以從類別的 **AllowedMembers** 清單選擇使用者、ou 和使用者群組做為聊天室管理員和成員，以管理及參與會議室。

在類別中建立的聊天室遵循類別 (所強制執行的原則和設定，例如誰可以在會議室的成員資格、誰可以管理該會議室、是否允許檔案上傳、是否已傳送邀請，等等) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

