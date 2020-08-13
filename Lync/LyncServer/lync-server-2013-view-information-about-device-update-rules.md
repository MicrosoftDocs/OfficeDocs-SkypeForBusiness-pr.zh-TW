---
title: Lync Server 2013：查看裝置更新規則的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa10335c21a943c90937306a39262e651c392a5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>在 Lync Server 2013 中查看裝置更新規則的相關資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

查看已匯入之裝置更新規則的詳細資料，包括更新適用于的裝置類型、模型和品牌。更新的版本和類型;以及更新的地區設定與集區。 資訊可用於所有已匯入的裝置更新規則（即將核准、已部署 (核准) 、召回 (還原) ，以及您決定不使用 (重設) ）。 從 Lync Server 控制台或 Windows PowerShell 存取這項資訊。

<div>


> [!NOTE]  
> 如需如何匯入、核准、重設、還原及移除規則的詳細資訊，請參閱<A href="lync-server-2013-device-update-rules.md">Lync Server 2013 中列出的裝置更新規則</A>主題。



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台查看裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**] 導覽按鈕。 匯入的規則會列在 [**裝置更新**] 頁面上。

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看裝置更新規則

您也可以使用 Windows PowerShell 和**Get-CsDeviceUpdateRule** Cmdlet 來查看所有裝置更新規則的詳細資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>若要查看您所有的裝置更新規則

  - 下列命令會傳回設定供組織使用之所有裝置更新規則的相關資訊：
    
        Get-CsDeviceUpdateRule
    
    命令會針對每個裝置更新規則傳回類似下列的資訊：
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>若要查看特定網頁伺服器上的所有裝置更新規則

  - 若要在特定電腦上查看裝置更新規則，請使用篩選參數後面接著伺服器身分識別及萬用字元 (\*) 。 例如：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

如需詳細資訊，請參閱[Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

