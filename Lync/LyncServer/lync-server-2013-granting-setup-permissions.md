---
title: Lync Server 2013：授與設定權限
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中授與設定權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-27_

您可以使用**Grant CsSetupPermission** Cmdlet，在指定的 Active Directory 組織單位（OU）中，為 RTCUniversalServerAdmins 群組新增讀取、寫入、ReadSPN 和 WriteSPN 許可權。 然後，該 OU 中 [RTCUniversalServerAdmins] 群組的成員可以安裝執行 Lync Server 2013 的伺服器，而不是 [網域管理員] 群組的成員。

使用**CsSetupPermission** Cmdlet 來驗證您使用**Grant CsSetupPermission** Cmdlet 設定的許可權。

您可以使用**Revoke CsSetupPermission** Cmdlet 來移除您使用**Grant CsSetupPermission** Cmdlet 所授予的許可權。

<div>

## <a name="to-grant-setup-permissions"></a>若要授與設定許可權

1.  在您想要授與設定許可權的網域中，登入執行 Lync Server 2013 的電腦。 如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    您可以指定 ComputerOu 參數，以相對於指定網域的預設命名內容（例如，CN = 電腦）。 或者，您也可以將此參數指定為完整的 OU 可分辨名稱（DN）（例如，「CN = 電腦，DC = Contoso，DC = com」）。 在後一個案例中，您必須指定與您指定之網域一致的 OU DN。
    
    如果您沒有指定 Domain 參數，則預設值為本地域。

</div>

<div>

## <a name="to-verify-setup-permissions"></a>驗證設定許可權

1.  在您想要驗證您使用**Grant CsSetupPermission** Cmdlet 所授出的安裝許可權之網域中，登入運行 Lync Server 2013 的電腦。 如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    您可以指定 ComputerOu 參數，以相對於指定網域的預設命名內容（例如，CN = 電腦）。 或者，您也可以將此參數指定為完整的 OU 可分辨名稱（DN）（例如，「CN = 電腦，DC = Contoso，DC = com」）。 在後一個案例中，您必須指定與您指定之網域一致的 OU DN。
    
    如果您沒有指定 Domain 參數，則預設值為本地域。

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>撤銷設定許可權

1.  在您想要吊銷**Grant CsSetupPermission** Cmdlet 所授的設定許可權的網域中，登入執行 Lync Server 2013 的電腦。 如果組織單位位於不同的子域中，請使用屬於網域管理員群組或企業系統管理員群組成員的帳戶。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    您可以指定 ComputerOu 參數，以相對於指定網域的預設命名內容（例如，CN = 電腦）。 或者，您也可以將此參數指定為完整的 OU 可分辨名稱（DN）（例如，「CN = 電腦，DC = Contoso，DC = com」）。 在後一個案例中，您必須指定與您指定之網域一致的 OU DN。
    
    如果您沒有指定 Domain 參數，則預設值為本地域。

</div>

</div>

<span> </span>

</div>

</div>

</div>

