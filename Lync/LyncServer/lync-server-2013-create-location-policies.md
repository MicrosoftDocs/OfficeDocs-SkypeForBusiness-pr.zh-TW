---
title: Lync Server 2013：建立位置原則
description: Lync Server 2013：建立位置原則。
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
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562259"
---
# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="6b8e5-103">在 Lync Server 2013 中建立位置原則</span><span class="sxs-lookup"><span data-stu-id="6b8e5-103">Create location policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b8e5-104">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="6b8e5-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="6b8e5-105">Lync Server 會使用位置原則，在用戶端註冊期間，啟用 E9-1-1 的 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-105">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="6b8e5-106">位置原則包含定義 E9-1-1 將如何執行的設定。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="6b8e5-107">您可以編輯全域位置原則，並建立新的標記位置原則。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-107">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="6b8e5-108">當用戶端不是位於關聯位置原則的子網內，或用戶端尚未直接指派位置原則時，用戶端會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-108">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="6b8e5-109">已將標記原則指派給子網或使用者。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-109">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="6b8e5-110">若要建立位置原則，您必須使用 RTCUniversalServerAdmins 群組成員的帳戶，或是 CsVoiceAdministrator 系統管理角色的成員，或具有相等的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-110">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="6b8e5-111">如需位置原則的完整說明，請參閱 [定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-111">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="6b8e5-112">此程式中的 Cmdlet 使用使用下列值定義的位置原則：</span><span class="sxs-lookup"><span data-stu-id="6b8e5-112">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b8e5-113">元素</span><span class="sxs-lookup"><span data-stu-id="6b8e5-113">Element</span></span></th>
<th><span data-ttu-id="6b8e5-114">值</span><span class="sxs-lookup"><span data-stu-id="6b8e5-114">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b8e5-115">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="6b8e5-115">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-116"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-116"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b8e5-117">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="6b8e5-117">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-118"><strong>免責聲明</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-118"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b8e5-119">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="6b8e5-119">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-120">您的公司原則需要您設定位置。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-120">Your company policy requires you to set a location.</span></span> <span data-ttu-id="6b8e5-121">如果您未設定位置，緊急服務將無法在緊急情況下找到您。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-121">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="6b8e5-122">請設定位置。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-122">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b8e5-123">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="6b8e5-123">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-124"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-124"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b8e5-125">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="6b8e5-125">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-126"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-126"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b8e5-127">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="6b8e5-127">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-128"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-128"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b8e5-129">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="6b8e5-129">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-130"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-130"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b8e5-131">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="6b8e5-131">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-132"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-132"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b8e5-133">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="6b8e5-133">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-134"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-134"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b8e5-135">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="6b8e5-135">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-136"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-136"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b8e5-137">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="6b8e5-137">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="6b8e5-138"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="6b8e5-138"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6b8e5-139">如需使用位置原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6b8e5-139">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="6b8e5-140">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6b8e5-140">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="6b8e5-141">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6b8e5-141">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="6b8e5-142">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6b8e5-142">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="6b8e5-143">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6b8e5-143">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="6b8e5-144">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="6b8e5-144">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="6b8e5-145">建立位置原則</span><span class="sxs-lookup"><span data-stu-id="6b8e5-145">To create location policies</span></span>

1.  <span data-ttu-id="6b8e5-146">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6b8e5-147">如果 <STRONG>PstnUsage</STRONG> 的設定尚未存在於 PstnUsages 的全域清單中，CsLocationPolicy 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-147">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="6b8e5-148">（選用）執行下列 Cmdlet 以編輯全域位置原則：</span><span class="sxs-lookup"><span data-stu-id="6b8e5-148">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="6b8e5-149">執行下列各項以建立標記位置原則。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-149">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="6b8e5-150">執行下列 Cmdlet，將在步驟3中建立的標記位置原則套用至使用者原則。</span><span class="sxs-lookup"><span data-stu-id="6b8e5-150">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

