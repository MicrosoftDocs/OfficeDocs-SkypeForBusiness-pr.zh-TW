---
title: Lync Server 2013：已在電腦、使用者或 InetOrgPerson 容器上停用許可權繼承
description: Lync Server 2013：已在電腦、使用者或 InetOrgPerson 容器上停用許可權繼承。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545159"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>已停用 Lync Server 2013 中電腦、使用者或 InetOrgPerson 容器的許可權繼承

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-19_

在鎖定的 Active Directory 網域服務中，使用者和電腦物件通常會放在特定的組織單位中 () Ou 中，以停用許可權繼承，以協助保護系統管理委派，並啟用群組原則物件 (Gpo) 以強制執行安全性原則。

網域準備和伺服器啟用設定 (Ace) Lync Server 2013 所需的存取控制專案。 當停用許可權繼承時，Lync Server 安全性群組無法繼承這些 Ace。 當這些許可權不是繼承時，Lync Server 安全性群組無法存取設定，而且會出現下列兩個問題：

  - 若要管理使用者、Inetorgperson 及連絡人，以及執行伺服器，Lync Server 安全性群組需要每個使用者之屬性集的網域準備程式設定 Ace、即時通訊 (RTC) 、RTC 使用者搜尋和公用資訊。 當停用許可權繼承時，安全性群組不會繼承這些 Ace，而且無法管理伺服器或使用者。

  - 若要探索伺服器及集區，執行 Lync Server 的伺服器依賴于電腦相關物件（包括 Microsoft 容器和伺服器物件）上的啟動所設定的 Ace。 當停用許可權繼承時，安全性群組、伺服器及集區不會繼承這些 Ace，而且不能利用這些 Ace。

若要解決這些問題，Lync Server 會提供 **Grant-CsOuPermission** Cmdlet。 這個 Cmdlet 會直接在指定的容器和組織單位上，以及容器或組織單位中的物件設定必要的 Lync Server Ace。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>在執行網域準備作業之後設定使用者、InetOrgPerson 及連絡人物件的許可權

在已停用許可權繼承的鎖定 Active Directory 環境中，網域準備不會在使用者或網域中的使用者或 InetOrgPerson 物件所在的容器或組織單位上，設定必要的 Ace。 在此情況下，您必須在具有已停用許可權繼承的使用者或 InetOrgPerson 物件的每個容器或 OU 上執行 **Grant-CsOuPermission** Cmdlet。 如果您有中央樹系拓撲，您也必須在保留連絡人物件的容器或 Ou 上執行此程式。 如需中央樹系拓撲的詳細資訊，請參閱支援檔中的 [支援的 Active Directory 拓撲（Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) ）。 ObjectType 參數會指定物件類型。 OU 參數會指定組織單位。

這個 Cmdlet 會直接在指定的容器或 Ou，以及容器中的使用者或 InetOrgPerson 物件上新增必要的 Ace。 如果執行此命令的 OU 具有使用者或 InetOrgPerson 物件的子 Ou，則不會對這些物件套用許可權。 您將需要個別于每個子 OU 上執行命令。 這是 Lync 主機部署的常見案例，例如上層 OU = OCS 租使用者、DC = CONTOSO、DC = LOCAL and child OU = Tenant1，OU = OCS 租，DC = CONTOSO，DC = LOCAL。

您需要與 Domain Admins 群組成員資格同等的使用者權限，才可執行此 Cmdlet。 如果已在鎖定的環境中移除已驗證的使用者 Ace，您必須在樹系根域中的相關容器或 Ou 上授與此帳戶讀取存取 Ace，如已 [驗證的使用者許可權已在 Lync Server 2013 中移除](lync-server-2013-authenticated-user-permissions-are-removed.md) ，或使用的是 Enterprise Admins 群組成員的帳戶。

**為 User、InetOrgPerson 及 Contact 物件設定必要的 Ace**

1.  使用 Domain Admins 群組的成員帳戶，或具有同等使用者權限的帳戶，登入加入網域的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  在記錄檔中，查看 **\<Success\>** 每個任務結尾的執行結果，確認已設定許可權，然後關閉 [記錄] 視窗。 或者，您可以執行下列命令來判斷是否已設定許可權：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>在執行網域準備之後設定電腦物件的許可權

在已停用許可權繼承的鎖定 Active Directory 環境中，網域準備不會在保留網域中電腦物件的容器或 Ou 上，設定必要的 Ace。 在此情況下，您必須在已停用許可權繼承的每個容器或 OU 上執行 **Grant-CsOuPermission** Cmdlet。 ObjectType 參數會指定物件類型。

此程式會直接在指定的容器上新增必要的 Ace。

您需要與 Domain Admins 群組成員資格同等的使用者權限，才可執行此 Cmdlet。 如果已移除已驗證的使用者 Ace，您必須授與樹系根域中相關容器上的此帳戶的讀取存取 Ace，如已 [驗證的使用者許可權已在 Lync Server 2013 中移除](lync-server-2013-authenticated-user-permissions-are-removed.md) ，或使用的是 Enterprise Admins 群組成員的帳戶。

**設定電腦物件所需的 Ace**

1.  使用 Domain Admins 群組的成員帳戶，或具有同等使用者權限的帳戶登入網域電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    如果不指定 Domain 參數，預設值為本機網域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  在記錄檔 C： \\ LogsOUPermissions.xml 範例中 \\ ，您會在 **\<Success\>** 每個工作結束時尋找執行結果，並確認沒有任何錯誤，然後關閉記錄。 您可以執行下列 Cmdlet 來測試許可權：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > 如果您在鎖定的 Active Directory 環境中，于樹系根域上執行網域準備，請注意，Lync Server 需要存取 Active Directory 架構和設定容器。<BR>如果已從 AD DS 中的架構或設定容器移除預設已驗證使用者許可權 &nbsp; ，則只有 Schema Admins 群組 (的架構容器) 或 Enterprise admins 群組的成員可以存取指定的容器，) 設定容器或 Enterprise admins 群組 (。 因為 Setup.exe、Lync Server 管理命令介面指令程式和 Lync Server 控制台需要存取這些容器，否則，除非執行安裝的使用者具有對 Schema Admins 和 Enterprise Admins 群組成員資格的使用者權限，否則系統管理工具將會失敗。<BR>若要修正此狀況，您必須授與 RTCUniversalGlobalWriteGroup 群組讀取、寫入架構和設定容器的許可權。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

