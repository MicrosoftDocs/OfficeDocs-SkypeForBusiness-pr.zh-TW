---
title: 使用類別以管理常設聊天室伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>使用類別以管理常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-01_

您的持續聊天伺服器部署可以主持許多併發持久聊天室。 聊天室在伺服器上會組織成一組類別。 每個聊天室各屬於一項類別，而且會繼承該類別中的一些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。

<div>


> [!NOTE]  
> 雖然您可以在執行持續聊天（Lync 用戶端）使用者的電腦上使用聊天室的許多管理功能，但持續聊天系統管理員（在<STRONG>cspersistentchatadministrator</STRONG>角色中）必須使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來建立或管理類別。



</div>

持續性聊天系統管理員使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別，以及針對組織中的使用者設計聊天室的存取權。

持久的聊天室管理員（能管理一或多個聊天室），可使用 Lync 用戶端啟動會議室管理 Web 應用程式來建立及管理會議室（或客戶可以建立要呼叫的自訂解決方案和工作流程）。 持續聊天管理員也可以使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理會議室。

<div>


> [!NOTE]  
> 持續聊天室不能與持續聊天類別具有相同的名稱。



</div>

聊天室管理員可以變更所有聊天室內容，但不能變更聊天室類別。無法限制其進行下列動作：

  - 停用聊天室

  - 變更聊天室名稱

  - 變更聊天室說明

  - 變更聊天室類型 (視聽形式或是一般形式)

  - 變更聊天室隱私權 (比較開放式、封閉式及祕密)

  - 新增或移除成員

  - 新增或移除聊天室管理員

  - 新增或移除增益集

  - 變更設定，例如邀請 (根據該類別所允許的設定)

<div>

## <a name="delegated-administration"></a>委派管理

使用正確的類別，就能更輕鬆地建立及管理持續聊天室。 持續性聊天管理員可以定義每個類別的**AllowedMembers**和**創意者**，也可以定義預設的聊天室設定和行為，這些動作會套用至在類別中建立的所有聊天室。 持續聊天系統管理員使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理類別。

允許以該類別建立聊天室的個人與群組，只有識別為該類別 Creators 的使用者、組織單位 (OU) 及使用者群組。建立類別之後，可以從類別的 **AllowedMembers** 清單中選擇使用者、OU 及使用者群組，做為管理和參與聊天室的聊天室管理員與成員。

在類別中建立的聊天室會遵守類別所強制的原則和設定（例如誰可以在會議室的成員資格、誰可以管理聊天室、是否允許檔案上傳、是否已傳送邀請等）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

