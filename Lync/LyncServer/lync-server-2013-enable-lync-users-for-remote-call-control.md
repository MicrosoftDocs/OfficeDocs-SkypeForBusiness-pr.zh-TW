---
title: Lync Server 2013：允許 Lync 使用者進行遠端呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="11c8b-102">在 Lync Server 2013 中允許 Lync 使用者進行遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="11c8b-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c8b-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="11c8b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="11c8b-104">您可以使用以伺服器為基礎的帶內提供原則，為遠端呼叫控制設定 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="11c8b-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="11c8b-105">您可以使用 Lync Server [控制台] 或 [Lync Server Management Shell] 命令列介面，管理頻帶內的提供設定。</span><span class="sxs-lookup"><span data-stu-id="11c8b-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="11c8b-106">這些工具會取代在舊版版本中用來管理群組原則設定的 Windows 管理工具（WMI）管理單元。</span><span class="sxs-lookup"><span data-stu-id="11c8b-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="11c8b-107">如果您想讓使用者在 Lync 中設定自己的遠端呼叫控制設定，您可以為伺服器上的使用者設定遠端通話控制設定，而不需指定**行伺服器 URI**和**行 URI**值。</span><span class="sxs-lookup"><span data-stu-id="11c8b-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="11c8b-108">請務必向您的使用者傳達適當的**線路伺服器 URI**與**行 uri**值，並為您的使用者提供設定這些設定的指示。</span><span class="sxs-lookup"><span data-stu-id="11c8b-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="11c8b-109">如需在 Lync Server 中手動設定遠端通話控制的程式，請參閱 Microsoft Office 網站上的 Lync <http://go.microsoft.com/fwlink/p/?linkid=210132>用戶端檔中的「設定手機選項和號碼」。</span><span class="sxs-lookup"><span data-stu-id="11c8b-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="11c8b-110">如果您有現有的通訊伺服器 2007 R2 或通訊伺服器2007部署，Communicator 2007 R2 和 Communicator 2007 用戶端將在並排遷移期間繼續使用 [群組原則]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="11c8b-111">不過，如果您想要將原則設定傳送到 Lync 用戶端，您必須設定對等的 Lync Server 內建配設設定。</span><span class="sxs-lookup"><span data-stu-id="11c8b-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11c8b-112">若要讓使用者能夠進行遠端通話控制，您必須為使用者提供 Line URI 和 Line Server URI。</span><span class="sxs-lookup"><span data-stu-id="11c8b-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="11c8b-113">如在<A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 中的遠端通話控制部署</A>工作中所述，您必須務必使用閘道在這些設定中所需的語法。</span><span class="sxs-lookup"><span data-stu-id="11c8b-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="11c8b-114">當您將靜態路由設定至閘道時，請確定線路伺服器 URI 中的網域與您在 MatchUri 參數中指定的目標網域相同。</span><span class="sxs-lookup"><span data-stu-id="11c8b-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="11c8b-115">Line URI 會以164格式指定指派給使用者的電話號碼，並使用 "電話：" 前置詞（例如電話： + 14255550150）。</span><span class="sxs-lookup"><span data-stu-id="11c8b-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="11c8b-116">如果您想要設定分機號碼，則該格式為電話： + 14255550150; ext = 111。</span><span class="sxs-lookup"><span data-stu-id="11c8b-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="11c8b-117">如果您先前已設定使用者的行 URI，而值並未變更，則當您啟用遠端通話控制的使用者時，不需要指定行 URI。</span><span class="sxs-lookup"><span data-stu-id="11c8b-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="11c8b-118">使用管理命令介面為啟用 Lync 的使用者啟用遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="11c8b-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="11c8b-119">登入 Lync Server 管理命令介面已安裝為 RTCUniversalServerAdmins 群組成員的電腦，或是您已指派**move-csuser** Cmdlet 的角色型存取控制角色。</span><span class="sxs-lookup"><span data-stu-id="11c8b-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="11c8b-120">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="11c8b-121">若要使用**move-csuser** Cmdlet 來設定現有 Lync 啟用的使用者的遠端通話控制，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="11c8b-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="11c8b-122">例如：</span><span class="sxs-lookup"><span data-stu-id="11c8b-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="11c8b-123">使用 Lync Server [控制台] 設定遠端通話控制的使用者</span><span class="sxs-lookup"><span data-stu-id="11c8b-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="11c8b-124">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="11c8b-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11c8b-125">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11c8b-126">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="11c8b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11c8b-127">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="11c8b-128">在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部（或第一個部分），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="11c8b-129">在表格中，按一下您要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="11c8b-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="11c8b-130">按一下 [**編輯**] 功能表上的 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="11c8b-131">在 [**電話**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="11c8b-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="11c8b-132">若要啟用遠端呼叫控制，讓使用者從 Lync 2013 控制其私人分支 exchange （PBX）電話，以進行 PC 對電腦音訊通話和 PC 對電話的通話，請按一下 [**遠端通話控制**]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="11c8b-133">在 [**行 URI**] 中，指定使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11c8b-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="11c8b-134">在 [ **Line SERVER URI**] 中，指定 SIP/CSTA 閘道的 sip URI。</span><span class="sxs-lookup"><span data-stu-id="11c8b-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="11c8b-135">若要啟用遠端通話控制，但停用 PC 對 PC 音訊通話，且要只讓使用者從 Lync 2013 控制其 PBX 手機，以進行 PC 到電話的通話，請按一下 [**僅限遠端通話控制**]。</span><span class="sxs-lookup"><span data-stu-id="11c8b-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="11c8b-136">在 [**行 URI**] 中，指定使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11c8b-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="11c8b-137">在 [ **Line SERVER URI**] 中，指定 SIP/CSTA 閘道的 sip URI。</span><span class="sxs-lookup"><span data-stu-id="11c8b-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="11c8b-138">完成後，請按一下 [ **Commit**] （提交）。</span><span class="sxs-lookup"><span data-stu-id="11c8b-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

