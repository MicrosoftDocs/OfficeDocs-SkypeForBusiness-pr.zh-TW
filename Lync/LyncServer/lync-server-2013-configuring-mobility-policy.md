---
title: Lync Server 2013：設定行動原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="1bdc4-102">在 Lync Server 2013 中設定行動原則</span><span class="sxs-lookup"><span data-stu-id="1bdc4-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bdc4-103">_**主題上次修改日期：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="1bdc4-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="1bdc4-104">Lync Server 2013 提供行動原則，可決定誰可以使用行動功能、透過公司通話、透過 IP （VoIP）或影片呼叫，以及 VoIP 或視頻是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="1bdc4-105">[透過工作通話] 功能可讓行動使用者使用公司電話號碼（而不是行動電話號碼）撥打及接聽行動電話上的通話。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="1bdc4-106">此功能可防止呼叫的參與方查看來電者的行動電話號碼，並讓使用者避免撥出電話費。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="1bdc4-107">設定 VoIP 和影片可讓使用者接收併發出 VoIP 通話和影片。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="1bdc4-108">WiFi 使用的設定定義使用者的裝置是否需要透過行動資料網路使用 WiFi 網路。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="1bdc4-109">根據預設，行動性、透過公司通話，以及 VoIP 與視頻功能都已啟用。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="1bdc4-110">已停用 [VoIp] 和 [影片] 需要 WiFi 的設定。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="1bdc4-111">系統管理員可以執行 Cmdlet 來判斷誰有權存取這些功能。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="1bdc4-112">您可以關閉 [全域]、[按網站] 或 [由使用者] 以外的選項。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="1bdc4-113">若要能夠使用行動功能及透過公司通話，使用者必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="1bdc4-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="1bdc4-114">必須針對 Lync Server 2013 啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="1bdc4-115">必須為使用者啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="1bdc4-116">必須將 [ **EnableMobility** ] 選項設定為 True 的行動原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="1bdc4-117">若要讓使用者能夠透過工作使用通話，他們必須滿足下列兩個額外的先決條件：</span><span class="sxs-lookup"><span data-stu-id="1bdc4-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="1bdc4-118">必須為使用者指派已選取 [**啟用同時撥打電話**] 選項的語音原則。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="1bdc4-119">必須將 [ **EnableOutsideVoice** ] 選項設定為 True 的行動原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1bdc4-120">未啟用企業語音的使用者可以使用他們的行動裝置，讓 Lync 透過 IP （VoIP）通話，或使用其行動裝置上的 [按一下以加入] 連結來加入會議（如果您為這些使用者指派了適當的語音原則選項）。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="1bdc4-121">如需詳細資訊，請參閱<A href="lync-server-2013-defining-your-mobility-requirements.md">定義 Lync Server 2013 的行動需求</A>。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1bdc4-122">如需有關啟用 Lync Server 2013 使用者的詳細資料，請參閱[停用或重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="1bdc4-123">如需有關啟用企業語音使用者的詳細資料，請參閱[在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="1bdc4-124">如需設定語音原則選項的詳細資料，請參閱[修改語音原則和設定 Lync Server 2013 中的 PSTN 使用記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="1bdc4-125">修改全域行動原則</span><span class="sxs-lookup"><span data-stu-id="1bdc4-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="1bdc4-126">登入 Lync Server 管理命令介面與 Ocscore 安裝為 CsAdministrator 角色成員的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="1bdc4-127">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1bdc4-128">在全球範圍內關閉行動與通話的存取權。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="1bdc4-129">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="1bdc4-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1bdc4-130">您可以透過工作關閉通話，而不需關閉行動存取權。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="1bdc4-131">不過，您也無法關閉行動，也不需要關閉 [透過工作通話]。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="1bdc4-132">依網站修改行動原則</span><span class="sxs-lookup"><span data-stu-id="1bdc4-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="1bdc4-133">登入 Lync Server 管理命令介面與 Ocscore 安裝為 CsAdministrator 角色成員的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="1bdc4-134">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1bdc4-135">建立網站層級原則，然後關閉 [VoIP] 和 [影片]，並啟用 [IP 音訊] 和 [依網站的 IP 視頻]。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="1bdc4-136">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="1bdc4-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="1bdc4-137">依使用者修改行動原則</span><span class="sxs-lookup"><span data-stu-id="1bdc4-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="1bdc4-138">登入 Lync Server 管理命令介面與 Ocscore 安裝為 CsAdministrator 角色成員的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="1bdc4-139">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1bdc4-140">建立使用者層級行動原則，並透過使用者的工作關閉行動與通話。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="1bdc4-141">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="1bdc4-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="1bdc4-142">您可以透過工作關閉通話，而不需關閉行動存取權。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="1bdc4-143">不過，您也無法關閉行動，也不需要關閉 [透過工作通話]。</span><span class="sxs-lookup"><span data-stu-id="1bdc4-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="1bdc4-144">例如：</span><span class="sxs-lookup"><span data-stu-id="1bdc4-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1bdc4-145">請參閱</span><span class="sxs-lookup"><span data-stu-id="1bdc4-145">See Also</span></span>


[<span data-ttu-id="1bdc4-146">停用或重新啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="1bdc4-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="1bdc4-147">在 Lync Server 2013 中啟用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="1bdc4-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="1bdc4-148">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="1bdc4-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="1bdc4-149">定義 Lync Server 2013 的行動需求</span><span class="sxs-lookup"><span data-stu-id="1bdc4-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="1bdc4-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1bdc4-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="1bdc4-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1bdc4-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="1bdc4-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1bdc4-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="1bdc4-153">授與 CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1bdc4-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="1bdc4-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1bdc4-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

