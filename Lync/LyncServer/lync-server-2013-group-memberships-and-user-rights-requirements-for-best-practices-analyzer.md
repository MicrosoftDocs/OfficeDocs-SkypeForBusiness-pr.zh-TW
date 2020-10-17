---
title: 最佳做法分析程式的群組成員資格和使用者權限需求
description: 最佳做法分析程式的群組成員資格和使用者權限需求。
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
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564189"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 中最佳做法分析程式的群組成員資格和使用者權限需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

若要成功執行最佳做法分析程式，您用來登入的使用者帳戶必須是本機電腦上管理員群組的成員。 此外，若要掃描您的環境，使用者帳戶必須是下列群組的成員：

  - **Domain Admins**    若要列舉 Active Directory 網域服務資訊，並呼叫 Windows Management Instrumentation (WMI) 提供者的網域控制站和通用類別目錄伺服器。

  - **管理員**    在每一部 Lync Server 2013 內部電腦及每一部 Edge Server 上都是必要的，可呼叫 Windows Management Instrumentation (WMI) 提供者和存取登錄。

  - **RTCUniversalReadOnlyAdmins**    已滿或已委派唯讀 Lync Server 2013 系統管理許可權。

  - **僅限 Exchange View 系統管理員**    「完全」或「委派 Exchange」只查看 Microsoft Exchange 組織的系統管理員。

如果您的使用者帳戶沒有足夠的使用者權限，您有兩個選項：

  - 在命令提示字元下，使用 **runas** 命令，以具備足夠使用者權限的帳戶來執行工具。 語法如下所示：
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - 在 [連線 **至 Active Directory]** 頁面上，設定您計畫用以執行最佳做法分析程式的帳號憑證。 按一下 **[顯示高級登入選項**]。 您可以輸入三個帳戶：一個用於連線至 Active Directory 網域服務，一個用於連線至 Lync Server 2013 Edge server，另一個則用於連接至 Exchange 伺服器。 如果您未指定任何這些帳戶，則會使用您用來登入和執行最佳做法分析程式的使用者帳戶。

</div>

<span> </span>

</div>

</div>

</div>

