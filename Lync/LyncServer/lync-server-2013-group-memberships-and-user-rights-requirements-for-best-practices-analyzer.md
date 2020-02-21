---
title: 群組的成員資格和最佳做法分析程式的使用者權限需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81dbf72e995291731c95749c3b1daecbf454190a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>群組的成員資格和 Lync Server 2013 中的最佳做法分析程式的使用者權限需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-21_

若要成功執行 Best Practices Analyzer，您用來登入的使用者帳戶必須是本機電腦上管理員群組的成員。 此外，來掃描您的環境，使用者帳戶必須是下列群組的成員：

  - **以 domain Admins**   列舉 Active Directory 網域服務的資訊，以及如何呼叫 Windows Management Instrumentation (WMI) 提供者在網域控制站和通用類別目錄伺服器。

  - **系統管理員**   呼叫 Windows Management Instrumentation (WMI) 提供者及存取登錄，每個 Lync Server 2013 內部電腦與每部 Edge Server 所需。

  - **RTCUniversalReadOnlyAdmins**   完整或委派讀取唯一的 Lync Server 2013 系統管理權限。

  - **Exchange 檢視僅限系統管理員**   完整或委派 Exchange 檢視僅限系統管理員在 Microsoft Exchange 組織。

如果您的使用者帳戶沒有足夠的權限，您會有兩個選項：

  - 在命令提示字元處，執行另一個帳戶沒有足夠的權限工具使用**runas**命令。 語法如下所示：
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - 在 [ **Active directory Connect** ] 頁面上，設定想要用來執行最佳做法分析程式的帳戶的認證。 按一下 [**顯示進階登入選項**]。 您可以輸入三個帳戶： 一個用於連線至 Active Directory 網域服務、 另一個適用於連線至 Lync Server 2013 Edge Server，和另一個適用於連線至 Exchange 伺服器。 如果您未指定任何這些帳戶，會使用您用來登入，並執行 Best Practices Analyzer 的使用者帳戶。

</div>

<span> </span>

</div>

</div>

</div>

