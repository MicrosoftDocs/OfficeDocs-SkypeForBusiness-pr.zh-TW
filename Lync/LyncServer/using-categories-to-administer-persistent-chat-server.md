---
title: 使用類別來管理常設聊天室伺服器
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
ms.openlocfilehash: 0e02a780772cd0e9592bb078ab526a4085a234bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>使用類別來管理常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-10-01_

Persistent Chat Server 部署可以裝載多個同時進行的常設聊天室。 聊天室可以在伺服器上組織成一組類別。 每個聊天室各屬於一個類別，並繼承該類別的某些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。

<div>


> [!NOTE]  
> 雖然有許多聊天室管理功能是用於執行使用者的常設聊天室 （Lync 用戶端） 的電腦，常設聊天室系統管理員 （ <STRONG>cspersistentchatadministrator</STRONG>角色） 必須使用 Lync Server 控制台或 Windows PowerShell cmdlet 來建立或管理類別。



</div>

常設聊天室系統管理員使用 Lync Server 控制台或 Windows PowerShell cmdlet 來建立及管理類別，以及設計聊天室的組織中使用者的存取權。

常設聊天室管理員，擁有管理一或多個聊天室的能力，可以使用 Lync 用戶端來啟動聊天室管理 Web 應用程式以建立及管理聊天室 （或客戶可以建立自訂解決方案和叫用的工作流程）。 常設聊天室系統管理員也可以使用 Lync Server 控制台或 Windows PowerShell cmdlet 建立及管理聊天室。

<div>


> [!NOTE]  
> 常設聊天室會議室不能有相同的常設聊天室類別的名稱。



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

## <a name="delegated-administration"></a>委派的管理

建立及管理常設聊天室就能輕鬆與類別的正確用法。 常設聊天室管理員可以針對每個類別定義**AllowedMembers**和**Creators** ，並將會套用至所有聊天室的類別中建立的行為與預設聊天室設定，也可以定義。 常設聊天室系統管理員建立並使用 Lync Server 控制台或 Windows PowerShell cmdlet 管理類別。

使用者、 組織單位 (Ou)，並會被識別為類別的建立者的使用者群組是唯一的個人和都可建立聊天室的類別中的群組。 建立類別之後，他們可以使用者、 Ou、 及使用者群組從清單中選擇類別**AllowedMembers**為聊天室管理員和成員可以管理和參與會議室。

類別中建立的聊天室遵守原則與設定強制提供的類別 （例如，誰具有聊天室的成員資格、 可以管理聊天室、 是否允許檔案上傳，是否要傳送邀請等）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

