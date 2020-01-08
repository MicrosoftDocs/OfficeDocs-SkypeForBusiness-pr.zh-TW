---
title: 最佳做法分析程式的群組成員資格與使用者權利需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013 中最佳做法分析程式的群組成員資格與使用者權利需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

若要成功執行最佳做法分析程式，您用來登入的使用者帳戶必須是本機電腦上系統管理員群組的成員。 此外，若要掃描您的環境，使用者帳戶必須是下列群組的成員：

  - **[網域管理員**   ] 可列舉 Active Directory 網域服務資訊，並在網網域控制站和通用類別目錄伺服器上呼叫 Windows Management Instrumentation （WMI）提供者。

  - ****    每個 Lync server 2013 內部電腦和每個邊緣伺服器所需的管理員都要呼叫 Windows Management Instrumentation （WMI）提供者，並存取登錄。

  - **RTCUniversalReadOnlyAdmins**   完整或委派的唯讀 Lync Server 2013 系統管理許可權。

  - **Exchange 僅適用**   于 Microsoft exchange 組織中的 [僅限系統管理員完全查看] 或 [委派 exchange Exchange 的管理員]。

如果您的使用者帳戶沒有足夠的使用者許可權，您有兩個選項：

  - 在命令提示字元中，使用**runas**命令，在擁有足夠使用者許可權的帳戶下執行該工具。 語法如下所示：
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - 在 [連線**至 Active Directory]** 頁面上，設定您打算用來執行最佳做法分析程式的帳號憑證。 按一下 **[顯示高級登入選項**]。 您可以輸入三個帳戶：一個用於連線至 Active Directory 網域服務，一個用於連線至 Lync Server 2013 Edge 伺服器，另一個用於連線到 Exchange 伺服器。 如果您沒有指定任何這些帳戶，就會使用您用來登入和執行最佳做法分析程式的使用者帳戶。

</div>

<span> </span>

</div>

</div>

</div>

