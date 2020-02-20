---
title: Lync Server 2013： 授與組織單位權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be8e2e96de97444364cb07169ce4276a7983f158
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>授與 Lync Server 2013 中的組織單位權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-05-14_

您可以使用**Grant-csoupermission** cmdlet 授與權限指定組織單位 (Ou) 中的物件，使樹系準備所建立的 RTC 萬用群組的成員可以存取其不需要以 Domain Admins 群組的成員。 新增至所指定 OU 的權限是相同的權限**Enable-csaddomain** cmdlet 新增至電腦和使用者在網域準備期間的容器。

使用**Test-csoupermission** cmdlet 來確認您使用**Grant-csoupermission** cmdlet 設定的權限。

您可以使用**Revoke-csoupermission** cmdlet 來移除您所使用**Grant-csoupermission** cmdlet 授與的權限。

<div>

## <a name="to-grant-ou-permissions"></a>若要授與 OU 權限

1.  登入您要授與 OU 權限的網域中執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

<div>

## <a name="to-verify-ou-permissions"></a>若要驗證 OU 權限

1.  登入您要驗證您使用**Grant-csoupermission** cmdlet 授與 OU 權限的網域中執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>若要撤銷 OU 權限

1.  登入您要撤銷 OU 權限已由**Grant-csoupermission** cmdlet 授與網域中執行 Lync Server 2013 的電腦。 如果 OU 位於不同的子網域，請使用 Domain Admins 群組或 Enterprise Admins 群組成員身分的帳戶。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

