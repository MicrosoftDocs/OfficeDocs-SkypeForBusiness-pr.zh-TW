---
title: Lync Server 2013：查看位置原則資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看位置原則資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在 Lync Server 2013 中，您可以使用位置原則來套用與增強版9-1-1 （E9-1）功能相關的設定，以及使用者或連絡人的位置設定。 位置原則會判斷使用者是否已啟用 E9-1-1，以及是否有緊急通話的行為。 例如，您可以使用位置原則來定義代表緊急通話的號碼（例如，911在美國）、企業安全性是否應該自動收到通知，以及如何路由通話。

您可以在 Lync Server 2013 [控制台] 的 [**網路**設定] 群組中設定位置原則。 在 Lync Server [控制台] 中，您可以查看、建立、修改或刪除位置原則。 使用下列程式來查看位置原則的相關資訊。 如需建立或修改位置原則的詳細資料，請參閱[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-view-information-about-a-location-policy"></a>若要查看位置原則的相關資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**位置原則**]。

4.  在 [**位置原則**] 頁面上，選取您要修改的位置原則。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。
    
    <div>
    

    > [!NOTE]  
    > 您一次只能查看一個位置原則的相關資訊。

    
    </div>

預設會存在單一原則，名為 Global，且無法刪除或重新命名。 不過，您可以修改全域原則。 除非您建立網站原則或依使用者原則，否則此原則會套用至所有使用者和連絡人。 每個使用者的原則都必須套用至特定的使用者。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md)  
[在 Lync Server 2013 中建立或修改網站](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

