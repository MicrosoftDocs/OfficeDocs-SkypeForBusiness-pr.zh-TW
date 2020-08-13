---
title: Lync Server 2013：將使用者移至另一個集區
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
ms.openlocfilehash: b103e2911812932026799bda154190aa6f46fc56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者移至另一個集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-02-09_

您可以使用 Lync Server 控制台將使用者指派至特定的伺服器或集區。

<div>


> [!TIP]  
> 將所有現有使用者從執行 Lync Server 2010 或更早版本的來源集區移至複雜 Active Directory 環境中的 Lync Server 2013 目的地集區，可能會導致 Active Directory 複寫速度變慢。 若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或更早版本的集區中移動使用者，也可以使用 Lync Server 管理命令介面來移動具有 Cmdlet 的使用者。 此外，篩選功能可與 Lync Server 2013 使用者搭配使用。



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>將選取的使用者移至不同的伺服器或集區

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。

5.  在表格中，選取清單中的特定使用者或使用者。

6.  在 [**動作**] 功能表上，按一下 [**將選取的使用者移至集**區]。

7.  在 [**移動使用者**] 中，選取要將使用者移至 [**目的地註冊區集**區] 的集區。

8.   (選用) 若目的地伺服器或集區無法使用，請選取 [**強制**] 核取方塊。
    
    <div>
    

    > [!Caution]  
    > 如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶會移動，但不會移動已排程會議和連絡人的相關使用者資料。

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>將一個伺服器或集區中的所有使用者移至不同的伺服器或集區

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [**動作**] 功能表上，按一下 [**將所有使用者移至集**區]。

5.  在 [**移動使用者**] 的 [**來源註冊集**區] 中，選取包含您要移動之使用者帳戶的集區。

6.  在 [**目的地登記集**區] 中，選取要將使用者移至其中的集區。

7.   (選用) 若目的地伺服器或集區無法使用，請選取 [**強制**] 核取方塊。
    
    <div>
    

    > [!Caution]  
    > 如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶會移動，但不會移動已排程會議和連絡人的相關使用者資料。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>若要使用篩選將使用者從一個集區移至另一個集區

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [**使用者搜尋**] 中，按一下 [**搜尋**]，然後按一下 [**新增篩選**]。

5.  在搜尋準則中，選取 [**註冊集**區]，選取 [**等於**]，選取 [目前的**集區 FQDN**]，然後按一下 [**尋找**]。

6.  在 [**動作**] 功能表上，按一下 [**將所有使用者移至集**區]。
    
    <div>
    

    > [!NOTE]  
    > 將篩選套用至現有的一組使用者時，選項 [<STRONG>將所有使用者移至</STRONG>集區] 是在篩選的使用者子集的內容中，而不是<STRONG><EM>所有</EM></STRONG>可能的使用者。

    
    </div>

7.  在 [**移動使用者**] 的 [**來源註冊集**區] 中，選取包含您要移動之使用者帳戶的集區。

8.  在 [**目的地登記集**區] 中，選取要將使用者移至其中的集區。

9.   (選用) 若目的地伺服器或集區無法使用，請選取 [**強制**] 核取方塊。
    
    <div>
    

    > [!Caution]  
    > 如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶會移動，但不會移動已排程會議和連絡人的相關使用者資料。

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 將使用者從一個集區移至另一個集區

1.  根據您執行 Windows PowerShell 命令的方式 (（本機或遠端) ），您必須以正確的 Lync Server 2013 系統管理角色的成員身分登入，如下所示：
    
    1.  如果您是在本機電腦上執行命令 (例如，您可以直接登入前端伺服器) ：登入安裝了 Lync Server 管理命令介面的電腦作為 RTCUniversalServerAdmins 群組的成員，或使用[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者權限。
    
    2.  如果您是在另一部電腦上遠端執行命令 (例如，登入您的電腦，然後從遠端的 Standard Edition 前端伺服器上執行命令) ：從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要移動單一使用者，請使用 Move-CsUser Cmdlet，如下所示：
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    若要移動的使用者為使用者 Pilar Ackerman，使用者將從目前指派的主集區移至集區 pool01.contoso.net

4.  若要移動大量的使用者，請搭配**Get-CsUser** Cmdlet 使用篩選器，並將產生的使用者集合傳遞給**Move-CsUser**：
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    **Get-CsUser**和**Move-CsUser**的合併命令可能會造成下列情況：
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中修改使用者帳戶屬性](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

