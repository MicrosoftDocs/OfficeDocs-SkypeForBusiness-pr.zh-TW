---
title: Lync Server 2013：建立或修改網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。 您可以使用 Microsoft Lync Server 2013 的 [控制台] 來設定網站，並將它們與區域建立關聯。 例如，北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。 您必須針對組織中的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制也一樣。 您可以從 Lync Server [控制台] 建立、修改及刪除網路網站。 使用下列程式來建立或修改網路網站。 如需刪除現有網路網站的詳細資訊，請參閱[在 Lync Server 2013 中刪除現有的網路網站](lync-server-2013-deleting-an-existing-network-site.md)。

<div>

## <a name="to-create-a-network-site"></a>建立網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上，按一下 [**新增**]。

5.  在 [**新增網站**] 的 [**名稱**] 欄位中，輸入此網站的名稱。
    
    <div>
    

    > [!NOTE]  
    > 網站名稱在 Lync Server 2013 部署中必須是唯一的。

    
    </div>

6.  在 [**地區**] 下拉式清單中，選取要與此網站建立關聯的網路區域。

7.  可選如果您想要將音訊或視頻通話的頻寬限制放到此網站，請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔和適當的設定。
    
    <div>
    

    > [!NOTE]  
    > 您可以在 [<STRONG>網路</STRONG>設定] 群組的 [<STRONG>原則設定檔</STRONG>] 頁面上，查看可用頻寬原則設定檔的詳細資料，或建立新的頻寬原則設定檔。 如需詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">在 Lync Server 2013 中建立或修改頻寬原則設定檔</A>。

    
    </div>

8.  可選如果您想要提供此網站的位置設定，請從 [**位置原則**] 下拉式清單中選取位置原則。
    
    <div>
    

    > [!NOTE]  
    > 位置原則會將特定的增強型9-1-1 （E9-1-1）及用戶端位置設定指派至網站。 您可以從 [<STRONG>網路</STRONG>設定] 群組的 [<STRONG>位置原則</STRONG>] 頁面，查看可用位置原則的詳細資料，或建立新的位置原則。 如需詳細資訊，請參閱<A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置原則資訊</A>。

    
    </div>

9.  可選在 [**描述**] 欄位中輸入一個值，以提供此網站的詳細資訊，而不能單獨以名稱表示。

10. 按一下 [認可]****。
    
    <div>
    

    > [!NOTE]  
    > 當您建立新的網路網站時，請不要使用<STRONG>相關聯的子網</STRONG>資料表。 當您建立或修改子網時，您可以將子網與網站建立關聯。 如需詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-network-subnets.md">在 Lync Server 2013 中建立或修改網路子網</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>修改網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上，按一下您要修改的網站。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯網站**] 頁面上，您可以修改與網站相關聯的描述、區域、頻寬原則設定檔，以及位置原則。 如需詳細資訊，請參閱本主題前面的「建立網路網站」一節。

7.  按一下 [認可]****。

您無法在此頁面上修改**關聯的子網**資料表。 相關子網的清單是為參考提供的，因此您在修改網站設定時，您會發現哪些子網會受到影響。

</div>

<div>

## <a name="to-delete-a-network-site"></a>刪除網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上，按一下您要刪除的網站。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的網站。 若要這樣做，請按住 CTRL 並在按住 CTRL 鍵的同時選取多個網站。 或者，若要選取 [所有網站]，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。
    
    <div>
    

    > [!WARNING]  
    > 如果網路網站與網路子網相關聯，您就無法移除它。 如果您嘗試移除與子網相關聯的網站，您會收到錯誤訊息。 若要查看網站是否與任何子網產生關聯，請按一下該網站，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中刪除現有的網路網站](lync-server-2013-deleting-an-existing-network-site.md)  


[新-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[移除-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

