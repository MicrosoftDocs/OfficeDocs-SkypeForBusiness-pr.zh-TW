---
title: Lync Server 2013： 報告 Kerberos 帳戶指派項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c742e6e7e5cedc773e0275700a738afd26a6777d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Lync Server 2013 中的報告 Kerberos 帳戶指派

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-01-16_

若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

您可以使用 **Get-CsKerberosAccountAssignment** Cmdlet 查詢 Kerberos 驗證帳戶指派項目相關資訊，並回報部署中目前指派項目相關資訊。

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>若要查詢網站的 Kerberos 驗證帳戶指派項目

1.  以 RTCUniversalServerAdmins 群組的成員，登入網域中執行 Lync Server 2013 或入已安裝系統管理工具的電腦的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  從命令列中執行下列其中一個命令：
    
      - 若要查詢組織裡所有 Kerberos 驗證帳戶指派項目，並傳回這些項目的個別指派資訊，請執行不含任何參數的 Cmdlet：
        
            Get-CsKerberosAccountAssignment
    
      - 若要查詢部署中所有 Kerberos 驗證帳戶指派項目，並傳回這些項目的個別網站指派資訊，請執行含 Identity 參數的 Cmdlet：
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        例如：
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 若要查詢單一網站中所有 Kerberos 驗證帳戶指派項目，並傳回這些項目的指派資訊，請執行含 Filter 參數的 Cmdlet：
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        例如：
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > 指定 Filter 參數的 *SiteName 會傳回在網站識別元的任意位置包含指定網站名稱之所有網站 (例如，在網站識別元中包含 Redmond 字串的所有網站) 的相關資訊。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

