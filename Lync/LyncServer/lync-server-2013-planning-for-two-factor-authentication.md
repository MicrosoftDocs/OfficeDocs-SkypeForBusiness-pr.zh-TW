---
title: Lync Server 2013： 規劃雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0738cb282ad2f1f375e89526fcdd1569a6707ad0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="aa622-102">規劃 Lync Server 2013 中的雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="aa622-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa622-103">_**主題上次修改日期：** 2015年-04-06_</span><span class="sxs-lookup"><span data-stu-id="aa622-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="aa622-104">以下是設定 Microsoft Lync Server 2013 環境以支援雙重要素驗證時的部署考量的清單。</span><span class="sxs-lookup"><span data-stu-id="aa622-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="aa622-105">用戶端支援</span><span class="sxs-lookup"><span data-stu-id="aa622-105">Client Support</span></span>

<span data-ttu-id="aa622-106">Lync Server 2013 的 Lync 2013 累計更新： 7 月 2013年桌面用戶端和行動裝置的所有用戶端目前支援雙重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="aa622-107">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="aa622-107">Topology Requirements</span></span>

<span data-ttu-id="aa622-108">客戶是我們強烈鼓勵讀者部署專用的 Lync Server 2013 使用 Lync Server 2013 的累計更新的雙因素驗證： 7 月 2013 Edge、 Director、 和使用者集區。</span><span class="sxs-lookup"><span data-stu-id="aa622-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="aa622-109">若要啟用 Lync 之使用者的被動驗證，就必須停用其他驗證方法的其他角色和服務，包括下列：</span><span class="sxs-lookup"><span data-stu-id="aa622-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa622-110">設定類型</span><span class="sxs-lookup"><span data-stu-id="aa622-110">Configuration Type</span></span></th>
<th><span data-ttu-id="aa622-111">服務類型</span><span class="sxs-lookup"><span data-stu-id="aa622-111">Service Type</span></span></th>
<th><span data-ttu-id="aa622-112">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="aa622-112">Server Role</span></span></th>
<th><span data-ttu-id="aa622-113">若要停用的驗證類型</span><span class="sxs-lookup"><span data-stu-id="aa622-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa622-114">Web 服務</span><span class="sxs-lookup"><span data-stu-id="aa622-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="aa622-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="aa622-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="aa622-116">Director</span><span class="sxs-lookup"><span data-stu-id="aa622-116">Director</span></span></p></td>
<td><p><span data-ttu-id="aa622-117">Kerberos、 NTLM、 和憑證</span><span class="sxs-lookup"><span data-stu-id="aa622-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa622-118">Web 服務</span><span class="sxs-lookup"><span data-stu-id="aa622-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="aa622-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="aa622-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="aa622-120">前端</span><span class="sxs-lookup"><span data-stu-id="aa622-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="aa622-121">Kerberos、 NTLM、 和憑證</span><span class="sxs-lookup"><span data-stu-id="aa622-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa622-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="aa622-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="aa622-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="aa622-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="aa622-124">銳利</span><span class="sxs-lookup"><span data-stu-id="aa622-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="aa622-125">Kerberos 及 NTLM</span><span class="sxs-lookup"><span data-stu-id="aa622-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa622-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="aa622-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="aa622-127">註冊機構</span><span class="sxs-lookup"><span data-stu-id="aa622-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="aa622-128">前端</span><span class="sxs-lookup"><span data-stu-id="aa622-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="aa622-129">Kerberos 及 NTLM</span><span class="sxs-lookup"><span data-stu-id="aa622-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa622-130">除非在服務層級停用這些驗證類型，所有其他版本的 Lync 用戶端將無法登入成功之後雙因素驗證您的部署中，已啟用內。</span><span class="sxs-lookup"><span data-stu-id="aa622-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="aa622-131">Lync 服務探索</span><span class="sxs-lookup"><span data-stu-id="aa622-131">Lync Service Discovery</span></span>

<span data-ttu-id="aa622-132">由內部及/或外部的用戶端用來探索 Lync 服務應設定為解析為雙因素驗證未啟用 Lync server 的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="aa622-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="aa622-133">與此組態中，來自未啟用雙因素驗證的 Lync 集區的使用者將不需要輸入 pin 碼，以進行驗證，而從雙因素驗證已啟用的 Lync 集區的使用者都必須輸入其 pin 碼以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="aa622-134">Exchange 驗證</span><span class="sxs-lookup"><span data-stu-id="aa622-134">Exchange Authentication</span></span>

<span data-ttu-id="aa622-135">已部署雙因素驗證 Microsoft exchange 的客戶可能會發現在 Lync 用戶端特定功能都無法使用。</span><span class="sxs-lookup"><span data-stu-id="aa622-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="aa622-136">這是目前的設計、 Lync 用戶端不支援雙重要素驗證取決於 Exchange 整合的功能。</span><span class="sxs-lookup"><span data-stu-id="aa622-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="aa622-137">Lync 連絡人</span><span class="sxs-lookup"><span data-stu-id="aa622-137">Lync Contacts</span></span>

<span data-ttu-id="aa622-138">Lync 使用者利用整合連絡人存放區功能設定會尋找值，其連絡人就無法再供之後登入雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="aa622-139">您應該使用**Invoke-csucsrollback** cmdlet 從整合連絡人存放區中移除現有的使用者連絡人，並將它們儲存在 Lync Server 2013 中，才能啟用雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="aa622-140">技能搜尋</span><span class="sxs-lookup"><span data-stu-id="aa622-140">Skill Search</span></span>

<span data-ttu-id="aa622-141">已設定的技能搜尋功能，其 Lync 環境中的客戶會尋找值，這項功能無法運作時 Lync 啟用的雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="aa622-142">這是經過設計，為 Microsoft SharePoint 目前不支援雙重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="aa622-143">Lync 認證</span><span class="sxs-lookup"><span data-stu-id="aa622-143">Lync Credentials</span></span>

<span data-ttu-id="aa622-144">有許多涉及可能會影響使用者設定為使用雙因素驗證儲存的 Lync 認證的部署考量。</span><span class="sxs-lookup"><span data-stu-id="aa622-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="aa622-145">刪除儲存的認證</span><span class="sxs-lookup"><span data-stu-id="aa622-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="aa622-146">桌面用戶端使用者應在 Lync 用戶端中使用 [**刪除我的登入資訊**] 選項，並從 %localappdata%刪除其 SIP 設定檔資料夾\\Microsoft\\Office\\15.0\\之前先嘗試使用雙因素驗證第一次登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="aa622-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="aa622-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="aa622-147">DisableNTCredentials</span></span>

<span data-ttu-id="aa622-148">使用 Kerberos 或 NTLM 驗證方法時，使用者的 Windows 認證可用自動進行驗證。</span><span class="sxs-lookup"><span data-stu-id="aa622-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="aa622-149">在一般 Lync Server 2013 部署中其中啟用 Kerberos 及/或 NTLM 驗證，使用者應該不需要輸入他們的認證登入每次。</span><span class="sxs-lookup"><span data-stu-id="aa622-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="aa622-150">如果不小心會提示使用者輸入認證提示他們輸入其 pin 碼之前， **DisableNTCredentials**登錄機碼可能會不小心設定用戶端電腦上，可能是透過群組原則。</span><span class="sxs-lookup"><span data-stu-id="aa622-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="aa622-151">若要防止其他認證提示，在本機工作站上建立下列登錄項目，或使用 Lync 系統管理範本套用至所有使用者使用 「 群組原則指定集區：</span><span class="sxs-lookup"><span data-stu-id="aa622-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="aa622-152">HKEY\_本機\_機器\\軟體\\原則\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="aa622-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="aa622-153">登錄\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="aa622-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="aa622-154">值： 0x0</span><span class="sxs-lookup"><span data-stu-id="aa622-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="aa622-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="aa622-155">SavePassword</span></span>

<span data-ttu-id="aa622-156">當使用者登入 Lync 第一次時，會提示使用者儲存他/她的密碼。</span><span class="sxs-lookup"><span data-stu-id="aa622-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="aa622-157">如果選取此選項可讓使用者的用戶端憑證] 若要儲存的個人憑證存放區和使用者的 Windows 認證會儲存認證管理員中的本機電腦中。</span><span class="sxs-lookup"><span data-stu-id="aa622-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="aa622-158">Lync 設定為支援雙重要素驗證時，應停用**SavePassword**登錄設定。</span><span class="sxs-lookup"><span data-stu-id="aa622-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="aa622-159">若要防止使用者儲存其密碼，請變更本機工作站上的下列登錄項目或使用 Lync 系統管理範本套用至所有使用者使用 「 群組原則指定集區：</span><span class="sxs-lookup"><span data-stu-id="aa622-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="aa622-160">HKEY\_目前\_使用者\\軟體\\Microsoft\\Office\\15.0\\Lync</span><span class="sxs-lookup"><span data-stu-id="aa622-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="aa622-161">登錄\_DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="aa622-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="aa622-162">值： 0x0</span><span class="sxs-lookup"><span data-stu-id="aa622-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="aa622-163">AD FS 2.0 Token 重新顯示</span><span class="sxs-lookup"><span data-stu-id="aa622-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="aa622-164">AD FS 2.0 提供稱為權杖重新執行偵測，依據多個語彙基元的要求使用相同語彙基元可以偵測，然後捨棄的功能。</span><span class="sxs-lookup"><span data-stu-id="aa622-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="aa622-165">啟用此功能時，權杖重新執行偵測會用來保護 WS-同盟被動式設定檔和 SAML WebSSO 設定檔中的驗證要求的完整性並確定相同語彙基元永遠不會使用一次以上。</span><span class="sxs-lookup"><span data-stu-id="aa622-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="aa622-166">應啟用此功能，在其中安全性是非常高的考量如下的情況下使用 kiosk 時。</span><span class="sxs-lookup"><span data-stu-id="aa622-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="aa622-167">權杖重新執行偵測的詳細資訊，請參閱最佳做法，Secure 規劃及部署的 AD FS 2.0 在[https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)。</span><span class="sxs-lookup"><span data-stu-id="aa622-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="aa622-168">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="aa622-168">External User Access</span></span>

<span data-ttu-id="aa622-169">設定 AD FS Proxy 或反向 Proxy，以支援 Lync 雙因素驗證來自外部網路是未深入涵蓋下列主題。</span><span class="sxs-lookup"><span data-stu-id="aa622-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

