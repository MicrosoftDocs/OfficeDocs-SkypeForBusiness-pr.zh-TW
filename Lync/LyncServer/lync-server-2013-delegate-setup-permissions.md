---
title: Lync Server 2013： 委派設定權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 394200b21d3720f288fc89780c6ff193bd278cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Lync Server 2013 中的委派設定權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

如果您不想要授與使用者或群組，已部署 Lync Server 2013 中的 Domain Admins 群組的成員資格，您可以啟用要執行**Enable-cstopology**的 RTCUniversalServerAdmins 群組的成員 執行 Lync Server 2013 的伺服器上的 Windows PowerShell cmdlet。 根據預設，以 RTCUniversalServerAdmins 群組的成員沒有執行此 cmdlet 的功能。 您系統管理員權限授與的權限執行 Lync Server 使用**Grant-cssetuppermission** cmdlet 並指定組織單位 (OU) 執行 Lync Server 2013 之伺服器的電腦物件的所在位置的伺服器上執行**Enable-cstopology** 。

當您安裝 Lync Server 的網域準備工作不會自動新增權限可讓執行 Enable-cstopology 指令程式，以 RTCUniversalServerAdmins 群組的成員。 這代表根據預設，您必須為網域系統管理員才能啟用拓樸。 您必須執行 Grant-CsSetupPermissions Cmdlet，才能給予 RTCUniversalServerAdmins 群組成員權限以啟用拓樸。 此外，您必須針對每一個 Active Directory 容器中會存放在執行 Lync Server 的電腦執行此 cmdlet。

請記住，這個 Cmdlet 只會將權限授與 RTCUniversalServerAdmins 群組；您無法使用這個 Cmdlet 將權限授與其他安全性群組或個別使用者。

<div>


> [!NOTE]  
> <STRONG>Enable-cstopology</STRONG>是允許 RTCUniversalServerAdmins 群組成員設定及部署 Lync Server 2013 的主要 cmdlet。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>若要新增至 RTCUniversalServerAdmins 群組執行 Enable-cstopology 的能力

1.  委派的使用者將執行**Enable-cstopology**的網域之 Domain Admins 群組成員身分登入伺服器。

2.  開啟 [Lync Server 2013 管理命令介面]。 Lync Server 2013 管理命令介面會自動安裝在每部前端伺服器或 Lync Server 2013 系統管理工具必須已安裝的任何電腦上。 如需 Lync Server 2013 管理命令介面的詳細資訊，請參閱作業文件中的[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)。

3.  從 Lync Server 2013 管理命令介面中執行下列 cmdlet:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > 如果 OU 不是最上層網站，您必須提供的完整網域名稱。

    
    </div>
    
    在下列範例中，OU 為"Lync Servers 」，也就是 contoso.com 網域中。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

