---
title: Lync Server 2013：查看會議配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 076c3a13f1cbc6519a0af4c0ee8b587a7f5d83ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5c6ac-102">在 Lync Server 2013 中查看會議配置設定</span><span class="sxs-lookup"><span data-stu-id="5c6ac-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c6ac-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5c6ac-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5c6ac-104">在 [Lync Server 2013 控制台] 中，您可以使用會議設定設定來控制如何在部署中實施會議。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="5c6ac-105">這包括下列會議設定：</span><span class="sxs-lookup"><span data-stu-id="5c6ac-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="5c6ac-106">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="5c6ac-107">選用的網站層級和使用者層級設定，可讓您建立及用來指定如何為特定網站或使用者實施會議。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="5c6ac-108">若要查看會議配置設定</span><span class="sxs-lookup"><span data-stu-id="5c6ac-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="5c6ac-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c6ac-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5c6ac-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5c6ac-112">在左導覽列中，按一下 [**會議**]，然後按一下 [**會議**設定]。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="5c6ac-113">在 [**會議**設定] 頁面上，按一下您要查看的會議設定。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="5c6ac-114">在 [**編輯檔案篩選**] 中，選取 [**顯示詳細資料]。**</span><span class="sxs-lookup"><span data-stu-id="5c6ac-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="5c6ac-115">核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-115">check box.</span></span>
    
    <span data-ttu-id="5c6ac-116">\*\*編輯會議設定- \< 原則 \> \*\*開啟顯示選取原則的設定。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="5c6ac-117">如需設定設定的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改會議配置設定的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5c6ac-118">使用 Windows PowerShell Cmdlet 來查看會議設定資訊</span><span class="sxs-lookup"><span data-stu-id="5c6ac-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5c6ac-119">您可以使用 Windows PowerShell 和 Get-CsMeetingConfiguration Cmdlet 來查看會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="5c6ac-120">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5c6ac-121">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="5c6ac-122">若要查看會議設定資訊</span><span class="sxs-lookup"><span data-stu-id="5c6ac-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="5c6ac-123">若要查看所有會議設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="5c6ac-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="5c6ac-124">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="5c6ac-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="5c6ac-125">如需詳細資訊，請參閱[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="5c6ac-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

