---
title: Lync Server 2013：將使用者移至另一個池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者移至另一個池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-02-09_

您可以使用 Lync Server [控制台]，將使用者指派給特定的伺服器或文件庫。

<div>


> [!TIP]  
> 將所有現有使用者從執行 Lync Server 2010 或較舊版本的來源池移至複雜作用中的 Active Directory 環境中的 Lync Server 2013 目的地池，可能會導致較慢的 Active Directory 複製。 若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或較舊版本的 pool 中移動使用者，或者您可以使用 Lync Server 管理命令介面來移動使用 Cmdlet 的使用者。 此外，篩選功能也可與 Lync Server 2013 使用者搭配使用。



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>若要將選取的使用者移至不同的伺服器或文件庫

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。

5.  在表格中，選取清單中特定的使用者或使用者。

6.  在 [**動作**] 功能表上，按一下 [**將選取的使用者移至資源庫**]。

7.  在 [**移動使用者**] 中，選取您要在 [**目的地註冊機構**] 中將使用者移至哪個池。

8.  可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。
    
    <div>
    

    > [!Caution]  
    > 如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶就會移動，但相關的使用者資料（例如，已安排的會議和連絡人）不會移動。

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>將所有使用者從一個伺服器或文檔池移至另一個伺服器或文檔池中

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。

5.  在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。

6.  在 [**目的地註冊機構] 池中**，選取您要將使用者移至哪個池。

7.  可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。
    
    <div>
    

    > [!Caution]  
    > 如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶就會移動，但相關的使用者資料（例如，已安排的會議和連絡人）不會移動。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>使用篩選將使用者從一個池中移到另一個池

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**使用者搜尋**] 中，按一下 [**搜尋**]，然後按一下 [**新增篩選**]。

5.  在搜尋準則中，選取 [**註冊機構池**]，選取 [**等於**]，選取 [**目前池 FQDN**]，然後按一下 [**尋找**]。

6.  在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。
    
    <div>
    

    > [!NOTE]  
    > 當篩選套用至現有的一組使用者時，會在篩選的使用者子集的內容（而非<STRONG><EM>所有</EM></STRONG>可能的使用者）中，選擇 [<STRONG>將所有使用者移至資源庫</STRONG>]。

    
    </div>

7.  在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。

8.  在 [**目的地註冊機構] 池中**，選取您要移動使用者的池。

9.  可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。
    
    <div>
    

    > [!Caution]  
    > 如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶就會移動，但相關的使用者資料（例如，已安排的會議和連絡人）不會移動。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 將使用者從一個池中移至另一個池

1.  視您執行的是 Windows PowerShell 命令（本機或遠端）而定，您需要以正確的 Lync Server 2013 管理角色的成員身分登入，如下所示：
    
    1.  如果您在本機電腦上執行命令（例如，您是直接登入前端伺服器）：登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組成員的電腦，或使用[Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者權利。
    
    2.  如果您是在另一部電腦遠端執行命令（例如，登入您的電腦，並在標準版前端伺服器上遠端執行命令）：從指派給 CsUserAdministrator 角色或 CsAdministrator 的使用者帳戶。角色，請登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要移動單一使用者，請使用 Move-csuser Cmdlet，如下所示：
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    使用者要移動的使用者是 Pilar 方，而使用者會從目前指派的主池中移至 [資源庫] pool01.contoso.net

4.  若要移動大量的使用者，請使用**move-csuser** Cmdlet 的篩選器，並將產生的使用者組傳遞到**move-csuser**：
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Move-csuser**和**move-csuser**的合併命令可能會造成下列情況：
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中修改使用者帳戶屬性](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

