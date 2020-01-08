---
title: Lync Server 2013：建立或修改網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路子網

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

網路子網必須與網路網站建立關聯，才能判斷屬於該子網上之主機的地理位置。 您可以使用 Lync Server [控制台] 來設定子網。 您可以從 Lync Server [控制台] 建立、修改或刪除網路子網。 如需有關刪除網路子網的詳細資訊，請參閱[在 Lync Server 2013 中刪除網路子網](lync-server-2013-deleting-network-subnets.md)。

在部署呼叫許可控制（CAC）的大多數 Microsoft Lync Server 2013 部署中，通常會有大量的子網。 因此，通常最好是從 Lync Server 管理命令介面設定子網。 您可以從該處呼叫**CsNetworkSubnet** ，並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。 透過搭配使用這些 Cmdlet，您就可以從逗號分隔值（.csv）檔案朗讀子網設定，並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-create-a-network-subnet"></a>建立網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上，按一下 [**新增**]。

5.  在 [**新子網**] 中，在 [**子網識別碼**] 欄位中輸入一個值。 這必須是 IP 位址（例如，174.11.12.0），而且必須是子網上所定義之 IP 位址範圍中的第一個位址。

6.  在 [ **Mask** ] （遮罩）欄位中，輸入介於1到32的數值。
    
    <div>
    

    > [!NOTE]  
    > 這個值是要套用至要建立之子網上的位元遮罩。

    
    </div>

7.  在 [**網路網站識別碼**] 中，選取此子網所屬的網站。

8.  可選在 [**描述**] 欄位中輸入一個值，以提供此子網無法單獨以名稱表示的詳細資訊。

9.  按一下 [認可]****。

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>修改網路子網

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。

4.  在 [**子網**] 頁面上，按一下您要修改的子網。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯子網**] 頁面上，您可以修改位元遮罩、相關的網路網站或描述。 如果您修改位元遮罩，請記住，子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[刪除 Lync Server 2013 中的網路子網](lync-server-2013-deleting-network-subnets.md)  


[關於 Lync Server 2013 中的網路區域、網站和子網路](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[新-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[移除-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

