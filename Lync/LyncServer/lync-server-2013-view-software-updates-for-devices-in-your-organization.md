---
title: Lync Server 2013：查看您組織中裝置的軟體更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1940f92860d5ccd2d66c53a0a4da16cebada24
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>在 Lync Server 2013 中查看裝置的軟體更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用 Lync Server 2013，您可以使用裝置更新 Web 服務來查看及管理組織裝置的軟體更新。 您可以從 Microsoft 支援網站的 .cab (機櫃) 檔案中取得這些更新 [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) 。 下載 .cab 檔案之後，請執行**Import-CSDeviceUpdate** Cmdlet 以從 .cab 檔案匯入裝置更新規則。 如需**Import-CSDeviceUpdate** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 。

<div>


> [!TIP]  
> 在將新的更新部署至您的組織之前，請確認測試裝置上的工作是否正常運作。



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>若要查看 UC 裝置的軟體更新

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  從 Microsoft 支援網站，將 [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) .cab 檔案下載至 Lync Server 2013 電腦上的某個位置 (例如，C： \\ Updates \\UCUpdates.cab) 。

3.  \\ \\ 執行下列其中一個 Cmdlet，從 C： UpdatesUCUpdates.cab 檔案匯入裝置更新規則：
    
      - 如果 .cab 檔案與執行服務的電腦位於相同的電腦上， (服務： Redmond-websvc-2) ，請執行下列 Cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - 如果 .cab 檔案位於不同的電腦上，而非執行服務的電腦要更新 (服務： Redmond-websvc-3) ，請執行下列 Cmdlet：
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

5.  在左導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**]。

6.  在 [**裝置更新**] 頁面上，按一下清單中的更新，然後執行下列其中一項操作：
    
      - **取消暫止的更新。** 若要防止選取的更新部署至您組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**解除擱置的更新**]。
    
      - **核准更新。** 若要允許選取的更新部署至您組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**核准**]。
    
      - **還原更新。** 若要允許先前核准的更新部署至您組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**還原**]。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

