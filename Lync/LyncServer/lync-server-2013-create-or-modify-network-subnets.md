---
title: Lync Server 2013：建立或修改網路子網
description: Lync Server 2013：建立或修改網路子網。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546919"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路子網

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

網路子網必須與網路網站相關聯，以判斷屬於該子網之主機的地理位置。 您可以使用 Lync Server 控制台設定子網。 在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路子網。 如需有關刪除網路子網的詳細資訊，請參閱 [刪除網路子網中的 Lync Server 2013](lync-server-2013-deleting-network-subnets.md)。

在大多數安裝通話許可控制 (CAC) 的 Microsoft Lync Server 2013 中，通常會有大量子網。 因此，通常最好是從 Lync Server 管理命令介面來設定子網。 從那裡，您可以將 **New-CsNetworkSubnet** 與 Windows PowerShell Cmdlet 匯 **入-CSV**搭配呼叫。 透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。 如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

<div>

## <a name="to-create-a-network-subnet"></a>建立網路子網

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。

4.  在 [ **子網** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **新建子網上**] 中，于 [ **子網識別碼** ] 欄位中輸入值。 這必須是 IP 位址 (例如，174.11.12.0) ，而且必須是子網定義之 IP 位址範圍中的第一個位址。

6.  在 [ **遮罩** ] 欄位中，輸入介於1到32的數值。
    
    <div>
    

    > [!NOTE]  
    > 這個值是要套用至所建立之子網的位元遮罩。

    
    </div>

7.  在 [ **網路網站識別碼**] 中，選取此子網所屬的網站。

8.   (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示之子網的詳細資訊。

9.  按一下 **[認可]**。

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>若要修改網路子網

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。

4.  在 [ **子網** ] 頁面上，按一下您要修改的子網。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯子網** ] 頁面上，您可以修改位元遮罩、關聯的網路網站或描述。 如果您修改位元遮罩，請記住子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除網路子網](lync-server-2013-deleting-network-subnets.md)  


[關於 Lync Server 2013 中的網路地區、網站和子網](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

