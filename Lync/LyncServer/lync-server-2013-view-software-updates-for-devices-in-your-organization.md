---
title: Lync Server 2013：查看貴組織中裝置的軟體更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>在 Lync Server 2013 中查看裝置的軟體更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用 Lync Server 2013，您可以使用裝置更新 Web 服務來查看及管理貴組織裝置的軟體更新。 這些更新在來自 Microsoft 支援網站的 .cab （檔櫃）檔案中提供[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)。 下載 .cab 檔案之後，請執行匯**入-CSDeviceUpdate** Cmdlet，從 .cab 檔案匯入裝置更新規則。 如需有關**Import CSDeviceUpdate** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[import CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 。

<div>


> [!TIP]  
> 在您的組織部署新的更新之前，請確認它能在測試裝置上正常運作。



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>若要查看 UC 裝置的軟體更新

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  從 Microsoft 支援網站[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)，將 .cab 檔案下載至 Lync Server 2013 電腦上的位置（例如，C：\\Updates\\UCUpdates）。

3.  執行下列其中一個 Cmdlet，從 C：\\Updates\\UCUpdates .cab 檔案匯入裝置更新規則：
    
      - 如果 .cab 檔案所在的電腦與執行要更新之服務的同一台電腦（服務：雷德蒙-websvc-2），請執行下列 Cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - 如果 .cab 檔案所在的電腦不同于執行要更新的服務的電腦（服務：雷德蒙-websvc-3），請執行下列 Cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

5.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**]。

6.  在 [**裝置更新**] 頁面上，按一下清單中的更新，然後執行下列其中一項操作：
    
      - **解除擱置中的更新。** 若要防止選取的更新部署到貴組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**解除擱置更新**]。
    
      - **核准更新。** 若要允許將所選的更新部署到貴組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**核准**]。
    
      - **還原更新。** 若要允許先前核准的更新部署到貴組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**還原**]。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

