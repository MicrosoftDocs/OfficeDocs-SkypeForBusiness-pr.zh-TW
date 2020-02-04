---
title: Lync Server 2013：Computers、Users 或 InetOrgPerson 容器已停用權限繼承
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Lync Server 2013 中的 Computers、Users 或 InetOrgPerson 容器已停用權限繼承

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-19_

在鎖定的 Active Directory 網域服務中，使用者和電腦物件通常都是以停用許可權繼承的特定組織單位（Ou）來進行，以協助保護系統管理委派，以及啟用群組原則物件（Gpo）的使用。強制執行安全性原則。

網域準備和伺服器啟用：設定 Lync Server 2013 所需的存取控制專案（Ace）。 當權限繼承停用時，Lync Server 安全性群組無法繼承這些 Ace。 如果不繼承這些許可權，Lync Server 安全性群組將無法存取設定，而且會發生下列兩個問題：

  - 若要管理使用者、InetOrgPersons 和連絡人，以及使用伺服器，Lync Server 安全性群組需要在每個使用者的屬性集、即時通訊（RTC）、RTC 使用者搜尋及公用資訊的網域準備程式中設定 Ace. 當權限繼承停用時，安全性群組不會繼承這些 Ace，也不能管理伺服器或使用者。

  - 若要探索伺服器和池，執行 Lync Server 的伺服器依賴在與電腦相關物件上啟用的 Ace，包括 Microsoft 容器和 Server 物件。 停用許可權繼承之後，安全性群組、伺服器和池就不會繼承這些 Ace，也不能利用這些 Ace。

為了解決這些問題，Lync Server 提供**授與 CsOuPermission** Cmdlet。 這個 Cmdlet 會將所需的 Lync Server Ace 直接設定在指定的容器、組織單位和容器或組織單位中的物件上。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>在執行網域準備之後，設定使用者、InetOrgPerson 和連絡人物件的許可權

在已停用許可權繼承的鎖定 Active Directory 環境中，[網域準備] 不會在擁有網域中的使用者或 InetOrgPerson 物件的容器或組織單位上，設定必要的 Ace。 在這種情況下，您必須在擁有已停用許可權繼承的使用者或 InetOrgPerson 物件的每個容器或 OU 上執行**Grant CsOuPermission** Cmdlet。 如果您有中央林拓朴，您也必須在擁有連絡人物件的容器或 Ou 上執行此程式。 如需中央林拓撲的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。 ObjectType 參數會指定物件類型。 OU 參數會指定組織單位。

這個 Cmdlet 會將所需的 Ace 直接新增到容器中指定的容器或 Ou，以及使用者或 InetOrgPerson 物件。 如果執行此命令的 OU 具有使用者或 InetOrgPerson 物件的子 Ou，則這些許可權不會套用在這些物件上。 您將需要個別在每個子 OU 上執行命令。 這是使用 Lync 主機部署的常見案例，例如父 OU = OCS 租使用者、DC = CONTOSO、DC = LOCAL 和 child OU = Tenant1，OU = OCS 承租人，DC = CONTOSO，DC = LOCAL。

您需要與 Domain 管理員群組成員資格同等的使用者權限，才能執行此 Cmdlet。 如果已在鎖定環境中移除經過驗證的使用者 Ace，您必須在[Lync Server 2013 中已移除已驗證的使用者許可權](lync-server-2013-authenticated-user-permissions-are-removed.md)，或使用企業系統管理員群組成員的帳戶，在林根網域的相關容器或 ou 中授與此帳戶讀取存取 ace。

**若要為使用者、InetOrgPerson 和連絡人物件設定必要的 Ace**

1.  使用網域系統管理員群組的成員或擁有同等使用者許可權的帳戶登入加入網域的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    如果您沒有指定 Domain 參數，則預設值為本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  在記錄檔中，在每個工作的結尾尋找** \<成功\> **執行結果，以確認許可權已設定，然後關閉 [記錄] 視窗。 或者，您可以執行下列命令來判斷是否已設定許可權：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>在執行網域準備之後，設定電腦物件的許可權

在已停用許可權繼承的鎖定 Active Directory 環境中，[網域準備] 不會在擁有網域中電腦物件的容器或 Ou 上設定必要的 Ace。 在這種情況下，您必須在運行 Lync Server 且已停用許可權繼承之電腦的每個容器或 OU 上執行**授與 CsOuPermission** Cmdlet。 ObjectType 參數會指定物件類型。

此程式會將所需的 Ace 直接新增到指定的容器。

您需要與 Domain 管理員群組成員資格同等的使用者權限，才能執行此 Cmdlet。 如果已移除經過驗證的使用者 Ace，您必須在林根網域的相關容器上授與此帳戶的讀取存取 Ace，如在[Lync Server 2013 中移除已驗證的使用者許可權，](lync-server-2013-authenticated-user-permissions-are-removed.md)或使用的是企業系統管理員群組成員的帳戶。

**若要設定電腦物件所需的 Ace**

1.  以網域系統管理員群組成員或具有同等使用者許可權的帳戶登入網域電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    如果您沒有指定 Domain 參數，則預設值為本地域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  在範例記錄檔案 C：\\記錄\\OUPermissions 中，您會在每個工作結束時尋找** \<成功\> **執行結果，並確認沒有錯誤，然後關閉記錄。 您可以執行下列 Cmdlet 來測試許可權：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > 如果您在已鎖定的 Active Directory 環境中，在林根網域上執行網域準備，請注意 Lync Server 需要存取 Active Directory 架構和配置容器。<BR>如果從 AD&nbsp;DS 中的架構或配置容器中移除預設的經過驗證的使用者許可權，則只有架構管理員群組的成員（適用于架構容器）或企業系統管理員群組（適用于配置容器）才能存取指定的容器。 因為 setup.exe、Lync Server 管理命令介面 Cmdlet 和 Lync Server 控制台需要存取這些容器，否則，除非執行安裝的使用者具有對架構的使用者權限，否則系統管理工具的安裝和安裝將會失敗。系統管理員和企業管理員群組成員資格。<BR>若要修正這種情況，您必須授與 RTCUniversalGlobalWriteGroup 群組讀取、寫入架構和配置容器的許可權。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

