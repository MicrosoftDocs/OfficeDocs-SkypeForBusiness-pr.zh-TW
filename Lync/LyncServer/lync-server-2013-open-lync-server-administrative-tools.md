---
title: Lync Server 2013：開啟 Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>開啟 Lync Server 2013 系統管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-28_

您可以使用本主題中的程式來開啟 [管理工具] 來部署、設定或疑難排解您的 Lync Server 2013 拓撲。

  - 部署嚮導

  - 拓撲建立器

  - Lync Server 控制台

  - Lync Server 管理命令介面

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>部署嚮導

使用下列程式在本機啟動部署嚮導，以新增或移除 Lync Server 2013 元件檔。

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>啟動 Lync Server 2013 部署嚮導

1.  登入 Lync Server 部署嚮導以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員的身分安裝的電腦。

2.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>拓撲建立器

使用下列程式開啟 [拓撲建立器]，以定義您要在 Lync Server 2013 拓撲結構中部署的伺服器。

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>開啟 Lync Server 2013 拓撲建立器以設計拓撲

1.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要讀取、發佈或啟用拓撲（需要在伺服器上安裝 Lync Server 2013），您必須使用網域系統管理員群組和 RTCUniv 成員的帳戶。ersalServerAdmins 群組，且在您要用於封存檔案存放區的檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲產生器可以設定必要的隨機存取控制清單（Dacl）。或具有同等使用者權限的帳戶。

    
    </div>

2.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 [控制台]

使用下列其中一個程式來開啟 Lync Server 2013 [控制台]，管理您環境中伺服器、使用者、用戶端和裝置的設定。

<div>


> [!NOTE]  
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶來執行 Lync Server 2013 [控制台] 中的任何任務。 您可以使用其他角色登入 Lync Server 2013 [控制台] 來執行特定的系統管理工作，視需要執行的工作而定。 例如，您可以使用 CSArchivingAdministrator 來管理 Lync Server 2013 [控制台] 中的 [存檔]。 如需有關角色的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。 如需可用於執行特定工作之角色的詳細資訊，請參閱該工作的相關檔。



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>從組織防火牆內的任何電腦開啟 Lync Server 2013 [控制台]

1.  從指派給 CsAdministrator 角色的使用者帳戶，或其他具有要執行之工作之許可權的角色，請以最小的螢幕解析度 1024 x 768 登入內部部署中的任何電腦。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您已設定管理簡單的統一資源定位器（URL），您可以從您組織防火牆內任何電腦上執行的網際網路瀏覽器存取 Lync Server 2013 [控制台]。 如需有關設定管理簡單 URL 的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-planning-for-simple-urls.md">簡單 2013 Url 規劃</A>，以及在部署檔中<A href="lync-server-2013-edit-or-configure-simple-urls.md">編輯或設定 lync server 2013 中的簡單 url</A> 。

    
    </div>

2.  開啟瀏覽器視窗，然後輸入為貴組織設定的管理員 URL。

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>若要在執行 Lync Server 2013 的電腦上開啟 Lync Server 2013 [控制台]

1.  如果使用者帳戶是 CsAdministrator 角色的成員或其他角色，且具有適當的使用者權利和許可權，且要執行該工作，請登入您已安裝 Lync Server 2013 的電腦，或者至少 Lync Server 2013 administrat[我的工具]。 若要設定設定，電腦的畫面解析度必須達到 1024 x 768 的最小值。

2.  啟動 Lync Server 2013 [控制台]：按一下 [**開始**]，按一下 [**所有程式**]，指向 [**管理工具**]，指向 [ **Microsoft Lync Server 2013**]，然後按一下 [ **Lync Server 2013 控制台**]。

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理命令介面

使用下列程式來開啟 Lync Server 2013 管理命令介面，以在您的環境中使用命令列來管理伺服器、使用者、用戶端和裝置。

<div>


> [!NOTE]  
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶來執行 Lync Server 2013 管理命令介面中的任何任務。 您可以使用其他角色登入，以執行特定的系統管理工作，視您需要執行的任務而定。 例如，您可以使用 CSArchivingAdministrator 來執行與封存管理相關的 Cmdlet。 如需有關角色的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。 如需可用於執行特定 Cmdlet 之角色的詳細資訊，請參閱 Cmdlet 的相關檔。<BR>您也可以使用 [RTCUniversalServerAdmins]、[RTCUniversalUserAdmins] 或 [RTCUniversalReadOnlyAdmins] 群組中的使用者帳戶來執行某些 Cmdlet （視 Cmdlet 而定）。



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>若要開啟 Lync Server 2013 管理命令介面

  - 如果您開啟的是 Windows PowerShell 視窗，而不是 Lync Server 2013 管理命令介面，預設就是您無法執行 Lync Server 2013 Cmdlet。 若要在 Windows PowerShell 中執行 Lync Server 2013 Cmdlet，請在 Windows PowerShell 命令提示字元輸入下列內容：
    
    `Import-Module Lync`

  - 啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

