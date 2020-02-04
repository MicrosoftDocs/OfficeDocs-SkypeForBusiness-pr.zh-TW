---
title: Lync Server 2013：建立位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c10244bb3a70f7218dc3967e7f4f134048024f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="b90fc-102">在 Lync Server 2013 中建立位置原則</span><span class="sxs-lookup"><span data-stu-id="b90fc-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b90fc-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="b90fc-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="b90fc-104">Lync Server 在用戶端註冊期間，使用位置原則來啟用 E9-1-1 的 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b90fc-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="b90fc-105">位置原則包含定義 E9-1-1 將如何實現的設定。</span><span class="sxs-lookup"><span data-stu-id="b90fc-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="b90fc-106">您可以編輯全域位置原則，並建立新的標記位置原則。</span><span class="sxs-lookup"><span data-stu-id="b90fc-106">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="b90fc-107">當用戶端不位於關聯位置原則的子網中，或用戶端尚未直接指派位置原則時，用戶端會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="b90fc-107">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="b90fc-108">已將標記的原則指派給子網或使用者。</span><span class="sxs-lookup"><span data-stu-id="b90fc-108">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="b90fc-109">若要建立位置原則，您必須使用一個帳戶，該帳戶是 RTCUniversalServerAdmins 群組的成員，或是 CsVoiceAdministrator 系統管理角色的成員，或是具有同等的管理員權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="b90fc-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="b90fc-110">如需位置原則的完整說明，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b90fc-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="b90fc-111">此程式中的 Cmdlet 使用使用下列值定義的位置原則：</span><span class="sxs-lookup"><span data-stu-id="b90fc-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b90fc-112">元件</span><span class="sxs-lookup"><span data-stu-id="b90fc-112">Element</span></span></th>
<th><span data-ttu-id="b90fc-113">值</span><span class="sxs-lookup"><span data-stu-id="b90fc-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b90fc-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="b90fc-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="b90fc-115"><strong>滿足</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b90fc-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="b90fc-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="b90fc-117"><strong>免責聲明</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b90fc-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="b90fc-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="b90fc-119">您的公司原則需要您設定位置。</span><span class="sxs-lookup"><span data-stu-id="b90fc-119">Your company policy requires you to set a location.</span></span> <span data-ttu-id="b90fc-120">如果您沒有設定位置，緊急服務將無法在緊急情況下找不到您。</span><span class="sxs-lookup"><span data-stu-id="b90fc-120">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="b90fc-121">請設定位置。</span><span class="sxs-lookup"><span data-stu-id="b90fc-121">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b90fc-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="b90fc-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="b90fc-123"><strong>虛假</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b90fc-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="b90fc-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="b90fc-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b90fc-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="b90fc-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="b90fc-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b90fc-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="b90fc-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="b90fc-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b90fc-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="b90fc-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="b90fc-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b90fc-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="b90fc-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="b90fc-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b90fc-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="b90fc-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="b90fc-135"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b90fc-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="b90fc-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="b90fc-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="b90fc-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b90fc-138">如需使用位置原則的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b90fc-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="b90fc-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b90fc-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="b90fc-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b90fc-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="b90fc-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b90fc-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="b90fc-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b90fc-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="b90fc-143">授與 CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b90fc-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="b90fc-144">建立位置原則</span><span class="sxs-lookup"><span data-stu-id="b90fc-144">To create location policies</span></span>

1.  <span data-ttu-id="b90fc-145">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b90fc-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b90fc-146">如果<STRONG>PstnUsage</STRONG>的設定尚不在 PstnUsages 的全域清單中，CsLocationPolicy 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b90fc-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="b90fc-147">或者，您也可以執行下列 Cmdlet 來編輯全域位置原則：</span><span class="sxs-lookup"><span data-stu-id="b90fc-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="b90fc-148">執行下列動作來建立標籤位置原則。</span><span class="sxs-lookup"><span data-stu-id="b90fc-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="b90fc-149">執行下列 Cmdlet，將步驟3中建立的標籤位置原則套用至使用者原則。</span><span class="sxs-lookup"><span data-stu-id="b90fc-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

