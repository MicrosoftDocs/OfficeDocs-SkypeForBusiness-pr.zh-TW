---
title: Lync Server 2013：設定行動性原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f54f701d46f9b3e6e8f268612d7dc555b2716d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512760"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="84700-102">在 Lync Server 2013 中設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="84700-102">Configuring mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84700-103">_**主題上次修改日期：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="84700-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="84700-104">Lync Server 2013 提供行動原則，可決定誰可以使用行動功能、撥打工作、透過 IP 語音 (VoIP) 或影片，以及 VoIP 或影片是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="84700-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="84700-105">「透過工作通話」功能可讓行動使用者使用公司電話號碼，而不是行動電話號碼，撥打和接聽行動電話。</span><span class="sxs-lookup"><span data-stu-id="84700-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="84700-106">這項功能可防止叫用方看到來電者的行動電話號碼，並可讓使用者避免撥出電話費用。</span><span class="sxs-lookup"><span data-stu-id="84700-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="84700-107">設定 VoIP 和影片可讓使用者接收及撥打 VoIP 通話和影片。</span><span class="sxs-lookup"><span data-stu-id="84700-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="84700-108">WiFi 使用狀況設定定義使用者的裝置是否需要透過行動電話資料網路使用 WiFi 網路。</span><span class="sxs-lookup"><span data-stu-id="84700-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="84700-109">預設會啟用行動性、呼叫透過工作，以及 VoIP 和影片功能。</span><span class="sxs-lookup"><span data-stu-id="84700-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="84700-110">已停用 WiFi 的 VoIp 和影片所需的設定。</span><span class="sxs-lookup"><span data-stu-id="84700-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="84700-111">系統管理員可以執行 Cmdlet 來決定哪些人可以存取這些功能。</span><span class="sxs-lookup"><span data-stu-id="84700-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="84700-112">您可以依網站或使用者來全域關閉選項。</span><span class="sxs-lookup"><span data-stu-id="84700-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="84700-113">若要能夠使用行動功能和「從公司撥號」功能，使用者必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="84700-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="84700-114">使用者必須啟用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="84700-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="84700-115">使用者必須能夠使用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="84700-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="84700-116">使用者必須被指派 [EnableMobility]\*\*\*\* 選項設為 True 的行動原則。</span><span class="sxs-lookup"><span data-stu-id="84700-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="84700-117">若要讓使用者能夠使用「從公司撥號」，使用者必須符合下列兩項先決條件：</span><span class="sxs-lookup"><span data-stu-id="84700-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="84700-118">使用者必須被指派已選取 [使電話同時響鈴]\*\*\*\* 選項的語音原則。</span><span class="sxs-lookup"><span data-stu-id="84700-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="84700-119">必須為使用者指派 **[EnableOutsideVoice]** 選項設為 True 的行動原則。</span><span class="sxs-lookup"><span data-stu-id="84700-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84700-120">未啟用 Enterprise Voice 的使用者可以使用行動裝置，將 Lync to Lync over IP (VoIP) 通話，或透過使用行動裝置上的 [加入] 連結（如果您為這些使用者指派語音原則的適當選項）來加入會議。</span><span class="sxs-lookup"><span data-stu-id="84700-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="84700-121">如需詳細資訊，請參閱 <A href="lync-server-2013-defining-your-mobility-requirements.md">定義您的 Lync Server 2013 行動需求</A>。</span><span class="sxs-lookup"><span data-stu-id="84700-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="84700-122">如需對 Lync Server 2013 啟用使用者的詳細資訊，請參閱 [Disable or 重新啟用 Lync server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="84700-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="84700-123">如需關於為使用者啟用 Enterprise Voice 的詳細資訊，請參閱 [Enable 使用者 For Enterprise voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="84700-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="84700-124">如需設定語音原則選項的詳細資訊，請參閱 [在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="84700-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="84700-125">修改全域行動原則</span><span class="sxs-lookup"><span data-stu-id="84700-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="84700-126">登入任何安裝 Lync Server 管理命令介面和 Ocscore.msi 為 CsAdministrator role 成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="84700-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="84700-127">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="84700-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="84700-p105">全域關閉對行動性和「從公司撥號」功能的存取權。在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="84700-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84700-p106">您不需要關閉對行動性的存取權，即可關閉「從公司撥號」。不過，如果您要關閉行動性，也必須關閉「從公司撥號」。</span><span class="sxs-lookup"><span data-stu-id="84700-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="84700-132">依網站修改行動原則</span><span class="sxs-lookup"><span data-stu-id="84700-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="84700-133">登入任何安裝 Lync Server 管理命令介面和 Ocscore.msi 為 CsAdministrator role 成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="84700-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="84700-134">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="84700-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="84700-135">建立網站層級原則，並關閉 VoIP 和影片，並啟用 IP 音訊和 IP 影片的必要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="84700-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="84700-136">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="84700-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="84700-137">依使用者修改行動原則</span><span class="sxs-lookup"><span data-stu-id="84700-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="84700-138">登入任何安裝 Lync Server 管理命令介面和 Ocscore.msi 為 CsAdministrator role 成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="84700-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="84700-139">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="84700-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="84700-p108">建立使用者層級行動原則，並依使用者關閉行動性和「從公司撥號」。在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="84700-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="84700-p109">您不需要關閉對行動性的存取權，即可關閉「從公司撥號」。不過，如果您要關閉行動性，也必須關閉「從公司撥號」。</span><span class="sxs-lookup"><span data-stu-id="84700-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="84700-144">例如：</span><span class="sxs-lookup"><span data-stu-id="84700-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84700-145">請參閱</span><span class="sxs-lookup"><span data-stu-id="84700-145">See Also</span></span>


[<span data-ttu-id="84700-146">停用或重新啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="84700-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="84700-147">在 Lync Server 2013 中啟用使用者的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="84700-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="84700-148">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="84700-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="84700-149">定義 Lync Server 2013 的行動需求</span><span class="sxs-lookup"><span data-stu-id="84700-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="84700-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="84700-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="84700-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="84700-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="84700-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="84700-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="84700-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="84700-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="84700-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="84700-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

