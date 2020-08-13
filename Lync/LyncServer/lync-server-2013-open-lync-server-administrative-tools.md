---
title: Lync Server 2013：開啟 Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 172d448b3967782226335a5a3b9a4066514b7a9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>開啟 Lync Server 2013 系統管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-28_

您可以使用本主題中的程式來開啟系統管理工具，以部署、設定或疑難排解 Lync Server 2013 拓撲。

  - 部署嚮導

  - 拓撲產生器

  - Lync Server 控制台

  - Lync Server 管理命令介面

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>部署嚮導

使用下列程式可在本機啟動部署嚮導，以新增或移除 Lync Server 2013 元件檔案。

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>啟動 Lync Server 2013 部署嚮導

1.  以 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的身分，登入安裝 Lync Server 部署嚮導的電腦。

2.  依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>拓撲產生器

使用下列程式開啟拓撲產生器，以定義您想要在 Lync Server 2013 拓撲中部署的伺服器。

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>開啟 Lync Server 2013 拓撲產生器以設計拓撲

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但可讀取、發佈或啟用拓撲，這是在伺服器上安裝 Lync Server 2013 所需的功能。您必須使用屬於 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，而且在要用於封存檔案存放區的檔案共用上具有「完全控制」許可權 (（即讀取、寫入及修改），讓拓撲產生器可以設定必要的自由存取控制清單 (dacl) ，或具有同等使用者權限的帳戶。) 

    
    </div>

2.  啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 控制台

使用下列其中一個程式開啟 Lync Server 2013 控制台，以管理環境中的伺服器、使用者、用戶端和裝置的設定。

<div>


> [!NOTE]  
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶，在 Lync Server 2013 控制台中執行任何工作。 您可以使用其他角色登入 Lync Server 2013 控制台，以執行特定的管理工作，取決於您需要執行的工作。 例如，您可以使用 CSArchivingAdministrator 管理 Lync Server 2013 控制台中的封存。 如需角色的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A>。 如需您可以用來執行特定工作的角色的詳細資訊，請參閱任務的檔。



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>從組織防火牆內部的任何電腦開啟 Lync Server 2013 控制台

1.  從指派給要執行之工作的 CsAdministrator 角色或其他角色的使用者帳戶，登入內部部署中的任何電腦，最小螢幕解析度為 1024 x 768。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您已將管理簡單的統一資源定位器設定 (URL) ，您可以從組織防火牆內任何電腦上執行的網際網路瀏覽器，存取 Lync Server 2013 控制台。 如需設定管理簡易 URL 的詳細資訊，請參閱部署檔中的規劃檔及<A href="lync-server-2013-edit-or-configure-simple-urls.md">編輯或設定 [Lync server 2013</A> ] 中的簡易 URLs 中的「<A href="lync-server-2013-planning-for-simple-urls.md">規劃 lync server 2013 中的簡易 URLs</A> 。

    
    </div>

2.  開啟瀏覽器視窗，然後輸入為您的組織設定的管理 URL。

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>在執行 Lync Server 2013 的電腦上開啟 Lync Server 2013 控制台

1.  從屬於 CsAdministrator 角色的成員或其他角色的使用者帳戶，其具有要執行之工作的適當使用者權限及許可權，登入已安裝 Lync Server 2013 的電腦，或至少是 Lync Server 2013 系統管理工具。 若要設定設定，電腦必須具有 1024 x 768 的最小螢幕解析度。

2.  啟動 Lync Server 2013 控制台：按一下 [**開始**]，按一下 [**所有程式**]，指向 [系統**管理工具**]，指向 [ **Microsoft Lync Server 2013**]，然後按一下 [ **Lync Server 2013 控制台**]。

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理命令介面

使用下列程式開啟 Lync Server 2013 管理命令介面，以使用命令列管理環境中的伺服器、使用者、用戶端和裝置。

<div>


> [!NOTE]  
> 您可以使用指派給 CsAdministrator 角色的使用者帳戶，在 Lync Server 2013 管理命令介面中執行任何工作。 您可以使用其他角色登入，以執行特定的管理工作，取決於您需要執行的工作。 例如，您可以使用 CSArchivingAdministrator 來執行與封存管理相關的 Cmdlet。 如需角色的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A>。 如需您可以用來執行特定 Cmdlet 的角色的詳細資訊，請參閱 Cmdlet 的檔。<BR>您也可以使用 RTCUniversalServerAdmins、RTCUniversalUserAdmins 或 RTCUniversalReadOnlyAdmins 群組中的使用者帳戶來執行某些 Cmdlet，視 Cmdlet 而定。



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>開啟 Lync Server 2013 管理命令介面

  - 如果您開啟 Windows PowerShell 視窗，而不是 Lync Server 2013 管理命令介面，則根據預設，您無法執行 Lync Server 2013 Cmdlet。 若要從 Windows PowerShell 內執行 Lync Server 2013 Cmdlet，請在 Windows PowerShell 命令提示字元處，輸入下列命令：
    
    `Import-Module Lync`

  - 啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

