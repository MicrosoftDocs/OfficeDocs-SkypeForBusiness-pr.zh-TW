---
title: Lync Server 2013： 在電腦、 使用者或 InetOrgPerson 容器權限繼承已停用
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
ms.openlocfilehash: 7c67bda331532a11904b3edec469bceaa7e4f15b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>在電腦、 使用者或 Lync Server 2013 中的 InetOrgPerson 容器已停用權限繼承

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-12 月 19 日_

在鎖定的 Active Directory 網域服務、 使用者和電腦物件通常放在特定組織單位 (Ou) 與停用來協助保護系統管理委派，並啟用使用群組原則物件 (Gpo) 的權限繼承若要強制執行安全性原則。

網域準備和伺服器啟用設定存取控制項目 (Ace) 所需的 Lync Server 2013。 停用權限繼承時，Lync Server 的安全性群組無法繼承這些 Ace。 當這些權限不會繼承而來時，Lync Server 安全性群組不能存取設定，並會產生下列兩個問題：

  - Lync Server 的安全性群組來管理使用者、 Inetorgperson 及連絡人，及操作伺服器，需要每位使用者的屬性集、 即時通訊 (RTC)、 RTC 使用者搜尋，以及公用資訊的網域準備程序來設定的 Ace. 當已停用權限繼承時，安全性群組不會繼承這些 Ace，並無法管理伺服器或使用者。

  - 若要探索伺服器和集區，在執行 Lync Server 的伺服器自信地仰賴所啟用的電腦相關的物件，包括 Microsoft 容器和伺服器物件上設定的 Ace。 停用權限繼承時，安全性群組、 伺服器和集區不會繼承這些 Ace 並無法利用這些 Ace。

若要解決這些問題，Lync 伺服器還提供**Grant-csoupermission** cmdlet。 此 cmdlet 會設定必要的 Lync Server Ace 直接在指定的容器及組織單位和內的容器或組織單位的物件。

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>設定權限的使用者、 InetOrgPerson 和 Contact 物件執行網域準備之後

其中權限繼承已停用，網域準備作業不會設定必要的 Ace 容器或組織單位保留使用者或 InetOrgPerson 鎖定的 Active Directory 環境中的網域內的物件。 在此情況下，您必須在每個容器或 OU 具有使用者或已停用與的權限繼承的 InetOrgPerson 物件執行**Grant-csoupermission** cmdlet。 如果您有在中央樹系拓撲，您也必須容器或 Ou 保留連絡人物件上執行此程序。 如需中央樹系拓撲的詳細資訊，請參閱支援文件中的[Lync Server 2013 中支援的 Active Directory 拓撲](lync-server-2013-supported-active-directory-topologies.md)。 ObjectType 參數會指定的物件類型。 OU 參數會指定組織單位。

此 cmdlet 會直接在指定的容器或 Ou，以及容器內的 User 或 InetOrgPerson 物件上新增必要的 Ace。 如果執行此命令時的 OU 的 User 或 InetOrgPerson 物件的子 Ou，將不會於這些套用權限。 您必須個別執行每一個子 OU 上的命令。 這是常見的案例與 Lync 主控部署例如上層 OU = OCS 租用戶，DC = CONTOSO，DC = LOCAL 和子 OU = Tenant1，OU = OCS 租用戶，DC = CONTOSO，DC = LOCAL。

您需要的使用者權限等同於 Domain Admins 群組成員資格，才能執行此 cmdlet。 如果已驗證的使用者 Ace 也已移除鎖定的環境中，您必須授與此帳戶相關容器的讀取權限 Ace 或[驗證使用者權限已移除 Lync Server 2013 中](lync-server-2013-authenticated-user-permissions-are-removed.md)所述的樹系根網域中的 Ou，或使用是 Enterprise Admins 群組成員的帳戶。

**若要設定所需的 Ace User、 InetOrgPerson 和 Contact 物件**

1.  登入已加入網域的 Domain Admins 群組成員或具有相等使用者權限的帳戶的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    如果不指定 Domain 參數，預設值為本機網域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  在 [記錄檔中，尋找**\<成功\>** 執行結果結尾的每個工作以驗證已設定的權限，，然後關閉 [記錄] 視窗。 或者，您可以執行下列命令，以判斷是否已設定的權限：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>執行網域準備之後設定電腦物件權限

在鎖定的 Active Directory 環境中已停用權限繼承，網域準備作業不會保留網域內的電腦物件的 Ou 的容器上設定必要的 Ace。 在此情況下，您必須在每個容器或 OU 已執行已停用權限繼承的 Lync Server 的電腦上執行**Grant-csoupermission** cmdlet。 ObjectType 參數會指定的物件類型。

此程序會直接在指定容器上新增必要的 Ace。

您需要的使用者權限等同於 Domain Admins 群組成員資格，才能執行此 cmdlet。 如果也已移除已驗證的使用者 Ace，您必須授與此帳戶[驗證的使用者權限會移除 Lync Server 2013 中](lync-server-2013-authenticated-user-permissions-are-removed.md)所述的樹系根網域中相關容器的讀取權限 Ace，或使用 Enterprise Admins 群組成員的帳戶。

**若要設定所需的 Ace computer 物件**

1.  登入以屬於 Domain Admins 群組的成員或具有相等使用者權限帳戶的網域電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    如果不指定 Domain 參數，預設值為本機網域。
    
    例如：
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  範例記錄檔 c:\\記錄\\OUPermissions.xml，您會尋找**\<成功\>** 執行結果結尾的每個工作並確認沒有任何錯誤，，然後關閉 [記錄檔。 您可以執行下列 cmdlet 來測試權限：
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    例如：
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > 如果您在鎖定的 Active Directory 環境中的樹系根網域上執行網域準備，請注意 Lync Server 需要的 Active Directory 架構和設定容器權限。<BR>預設驗證使用者的權限，則會移除結構描述或組態容器中 AD&nbsp;DS，只有 Schema Admins 群組成員 （適用於結構描述容器） 或 （適用於 Configuration] 容器中） 的 Enterprise Admins 群組有權存取指定的容器。 因為 Setup.exe，Lync Server 管理命令介面指令程式，以及 Lync Server 控制台需要存取這些容器，否則執行安裝的使用者具有等同於結構描述的使用者權限，則將會失敗的系統管理工具的設定和安裝Admins 與 Enterprise Admins 群組成員資格。<BR>若要補救這種情況下，您必須授與 RTCUniversalGlobalWriteGroup 群組的讀取和寫入存取權的架構和設定容器。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

