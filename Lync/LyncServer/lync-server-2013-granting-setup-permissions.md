---
title: Lync Server 2013： 授與安裝程式權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014af4f0e03a8d49e3d08c68cff169283bd007bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>授與 Lync Server 2013 中的設定權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 08 月 27 日_

您可使用 **Grant-CsSetupPermission** Cmdlet，新增 Read、Write、ReadSPN 和 WriteSPN 權限給特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 群組。 然後 OU 可以安裝在指定的網域中執行 Lync Server 2013，不需要以 Domain Admins 群組的成員伺服器中使用 RTCUniversalServerAdmins 群組的成員。

使用 **Test-CsSetupPermission** Cmdlet，可以驗證您以 **Grant-CsSetupPermission** Cmdlet 設定的權限。

您可使用 **Revoke-CsSetupPermission** Cmdlet，移除您以 **Grant-CsSetupPermission** Cmdlet 授與的權限。

<div>

## <a name="to-grant-setup-permissions"></a>授與安裝程式權限

1.  登入您要設定權限授與網域中執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    您可將 ComputerOu 參數指定為相對於指定網域的預設命名內容 (例如 CN=computers)。或者，也可以將此參數指定為完整的 OU 辨別名稱 (DN) (例如 "CN=computers,DC=Contoso,DC=com")。若為後者，您指定的 OU DN 必須與所指定網域維持一致。
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

<div>

## <a name="to-verify-setup-permissions"></a>確認安裝程式權限

1.  登入您要驗證您使用**Grant-cssetuppermission** cmdlet 授與的安裝程式權限的網域中執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    您可將 ComputerOu 參數指定為相對於指定網域的預設命名內容 (例如 CN=computers)。或者，也可以將此參數指定為完整的 OU 辨別名稱 (DN) (例如 "CN=computers,DC=Contoso,DC=com")。若為後者，您指定的 OU DN 必須與所指定網域維持一致。
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>撤銷安裝程式權限

1.  登入您要撤銷已授與**Grant-cssetuppermission** cmdlet 的安裝程式權限的網域中執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    您可將 ComputerOu 參數指定為相對於指定網域的預設命名內容 (例如 CN=computers)。或者，也可以將此參數指定為完整的 OU 辨別名稱 (DN) (例如 "CN=computers,DC=Contoso,DC=com")。若為後者，您指定的 OU DN 必須與所指定網域維持一致。
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

