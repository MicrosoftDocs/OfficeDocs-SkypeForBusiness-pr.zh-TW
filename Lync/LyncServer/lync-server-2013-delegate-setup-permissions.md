---
title: Lync Server 2013：委派設定許可權
description: Lync Server 2013：委派設定許可權。
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
ms.openlocfilehash: a7038cf729bad459dbcd2a84a308b14aa56b68dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545339"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中委派設定許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

如果您不想要將 Domain Admins 群組的成員資格授與部署 Lync Server 2013 的使用者或群組，您可以啟用 RTCUniversalServerAdmins 群組的成員，以**Enable-CsTopology**   在執行 lync server 2013 的伺服器上執行 Enable-CsTopology Windows PowerShell Cmdlet。 根據預設，RTCUniversalServerAdmins 群組的成員不具備執行此 Cmdlet 的能力。 在執行 Lync Server 的伺服器上，使用**Grant-CsSetupPermission**指令程式，並指定組織單位 (OU) （位於執行 lync server 2013 之伺服器的電腦物件所在的位置），授與系統管理員的許可權，以執行**Enable-CsTopology** 。

安裝 Lync Server 時所進行的網域準備不會自動新增允許 RTCUniversalServerAdmins 群組成員執行 Enable-CsTopology Cmdlet 的許可權。 這代表根據預設，您必須為網域系統管理員才能啟用拓樸。 您必須執行 Grant-CsSetupPermissions Cmdlet，才能給予 RTCUniversalServerAdmins 群組成員權限以啟用拓樸。 此外，您需要針對駐留執行 Lync Server 之電腦的每個 Active Directory 容器執行此 Cmdlet。

請記住，這個 Cmdlet 只會將權限授與 RTCUniversalServerAdmins 群組；您無法使用這個 Cmdlet 將權限授與其他安全性群組或個別使用者。

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> 是允許 RTCUniversalServerAdmins 群組成員設定及部署 Lync Server 2013 的金鑰 Cmdlet。



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>新增執行 Enable-CsTopology 至 RTCUniversalServerAdmins 群組的能力

1.  以委派使用者將在其上執行之網域的 Domain Admins 群組成員身分登入伺服器 **Enable-CsTopology**。

2.  開啟 [Lync Server 2013 管理命令介面]。 Lync Server 2013 管理命令介面會自動安裝在每一部前端伺服器或已安裝 Lync Server 2013 系統管理工具的任何電腦上。 如需 Lync Server 2013 管理命令介面的詳細資訊，請參閱 Operations 檔中的 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面。

3.  從 Lync Server 2013 管理命令介面執行下列 Cmdlet：
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > 如果 OU 不是最上層，您必須提供完整的功能變數名稱。

    
    </div>
    
    在下列範例中，OU 為 "Lync Servers" （位於 contoso.com 網域中）。
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

