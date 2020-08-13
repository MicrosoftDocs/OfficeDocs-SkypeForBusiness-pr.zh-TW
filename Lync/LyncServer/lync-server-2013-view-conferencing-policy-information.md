---
title: Lync Server 2013：查看會議原則資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664078db23ecba5d26852c2e1348935a3e4c60b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="86b46-102">在 Lync Server 2013 中查看會議原則資訊</span><span class="sxs-lookup"><span data-stu-id="86b46-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b46-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="86b46-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="86b46-104">在 [Lync Server 2013 控制台] 中，您可以使用會議原則來控制如何在部署中實施會議。</span><span class="sxs-lookup"><span data-stu-id="86b46-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="86b46-105">這包括下列會議原則：</span><span class="sxs-lookup"><span data-stu-id="86b46-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="86b46-106">當您部署 Lync Server 2013 時，預設會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="86b46-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="86b46-107">選用的網站層級和使用者層級原則，可供您建立及使用，以指定如何為特定網站或使用者實施會議。</span><span class="sxs-lookup"><span data-stu-id="86b46-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="86b46-108">若要查看會議原則設定</span><span class="sxs-lookup"><span data-stu-id="86b46-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="86b46-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="86b46-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="86b46-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="86b46-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="86b46-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="86b46-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="86b46-112">請在左導覽列中按一下 **[會議]**，然後按一下 **[會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="86b46-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="86b46-113">在 [**會議原則**] 頁面上，連按兩下您要查看的會議原則。</span><span class="sxs-lookup"><span data-stu-id="86b46-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="86b46-114">在 [**編輯檔案篩選**] 中，選取 [**顯示詳細資料]。**</span><span class="sxs-lookup"><span data-stu-id="86b46-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="86b46-115">核取方塊。</span><span class="sxs-lookup"><span data-stu-id="86b46-115">check box.</span></span>
    
    <span data-ttu-id="86b46-116">\*\*編輯會議原則- \< 原則 \> \*\*開啟顯示選取原則的設定。</span><span class="sxs-lookup"><span data-stu-id="86b46-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="86b46-117">如需設定設定的詳細資訊，請參閱[建立或修改 Lync Server 2013 中的會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="86b46-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="86b46-118">使用 Windows PowerShell Cmdlet 來查看會議原則</span><span class="sxs-lookup"><span data-stu-id="86b46-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="86b46-119">您可以使用 Windows PowerShell 和 Get-CsConferencingPolicy Cmdlet 來查看會議原則。</span><span class="sxs-lookup"><span data-stu-id="86b46-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="86b46-120">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86b46-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="86b46-121">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="86b46-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="86b46-122">若要查看會議原則</span><span class="sxs-lookup"><span data-stu-id="86b46-122">To view conferencing policies</span></span>

  - <span data-ttu-id="86b46-123">若要查看所有會議原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="86b46-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="86b46-124">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="86b46-124">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="86b46-125">如需詳細資訊，請參閱[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="86b46-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

