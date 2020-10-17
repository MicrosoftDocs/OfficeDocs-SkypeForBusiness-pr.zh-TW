---
title: Lync Server 2013：規劃雙因素驗證
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
ms.openlocfilehash: 1932164cd1236257bbb81d1503b0310c8c55526e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513450"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="286e1-102">在 Lync Server 2013 中規劃雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="286e1-102">Planning for two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="286e1-103">_**主題上次修改日期：** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="286e1-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="286e1-104">以下是設定 Microsoft Lync Server 2013 環境以支援雙因素驗證時的部署考慮清單。</span><span class="sxs-lookup"><span data-stu-id="286e1-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="286e1-105">用戶端支援</span><span class="sxs-lookup"><span data-stu-id="286e1-105">Client Support</span></span>

<span data-ttu-id="286e1-106">Lync Server 2013 的 Lync 2013 累計更新：7月2013桌面用戶端和所有行動用戶端目前都支援雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="286e1-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="286e1-107">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="286e1-107">Topology Requirements</span></span>

<span data-ttu-id="286e1-108">客戶強烈建議使用專用的 Lync Server 2013 （含 Lync Server 2013 的累計更新）來部署雙因素驗證：7月 2013 Edge、Director 和使用者集區。</span><span class="sxs-lookup"><span data-stu-id="286e1-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="286e1-109">若要對 Lync 使用者啟用被動式驗證，其他角色和服務必須停用其他驗證方法，包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="286e1-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="286e1-110">配置類型</span><span class="sxs-lookup"><span data-stu-id="286e1-110">Configuration Type</span></span></th>
<th><span data-ttu-id="286e1-111">服務類型</span><span class="sxs-lookup"><span data-stu-id="286e1-111">Service Type</span></span></th>
<th><span data-ttu-id="286e1-112">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="286e1-112">Server Role</span></span></th>
<th><span data-ttu-id="286e1-113">要停用的驗證類型</span><span class="sxs-lookup"><span data-stu-id="286e1-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="286e1-114">Web 服務</span><span class="sxs-lookup"><span data-stu-id="286e1-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="286e1-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="286e1-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="286e1-116">Director</span><span class="sxs-lookup"><span data-stu-id="286e1-116">Director</span></span></p></td>
<td><p><span data-ttu-id="286e1-117">Kerberos、NTLM 和憑證</span><span class="sxs-lookup"><span data-stu-id="286e1-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="286e1-118">Web 服務</span><span class="sxs-lookup"><span data-stu-id="286e1-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="286e1-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="286e1-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="286e1-120">前端</span><span class="sxs-lookup"><span data-stu-id="286e1-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="286e1-121">Kerberos、NTLM 和憑證</span><span class="sxs-lookup"><span data-stu-id="286e1-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="286e1-122">代理</span><span class="sxs-lookup"><span data-stu-id="286e1-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="286e1-123">Edgeserver atl-edge</span><span class="sxs-lookup"><span data-stu-id="286e1-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="286e1-124">銳利</span><span class="sxs-lookup"><span data-stu-id="286e1-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="286e1-125">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="286e1-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="286e1-126">代理</span><span class="sxs-lookup"><span data-stu-id="286e1-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="286e1-127">處長</span><span class="sxs-lookup"><span data-stu-id="286e1-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="286e1-128">前端</span><span class="sxs-lookup"><span data-stu-id="286e1-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="286e1-129">Kerberos 和 NTLM</span><span class="sxs-lookup"><span data-stu-id="286e1-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="286e1-130">除非在服務層級停用這些驗證類型，否則在您的部署中啟用兩個要素驗證之後，所有其他版本的 Lync 用戶端將無法順利登入。</span><span class="sxs-lookup"><span data-stu-id="286e1-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="286e1-131">Lync 服務探索</span><span class="sxs-lookup"><span data-stu-id="286e1-131">Lync Service Discovery</span></span>

<span data-ttu-id="286e1-132">內部和/或外部用戶端使用的 DNS 記錄若要探索 Lync 服務，應設定為解析為未啟用雙因素驗證的 Lync server。</span><span class="sxs-lookup"><span data-stu-id="286e1-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="286e1-133">在此設定中，未啟用雙因素驗證的 Lync 集區中的使用者不需要輸入 PIN 碼以進行驗證，而啟用兩個要素驗證的 Lync 集區中的使用者則必須輸入其 PIN 碼以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="286e1-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="286e1-134">Exchange 驗證</span><span class="sxs-lookup"><span data-stu-id="286e1-134">Exchange Authentication</span></span>

<span data-ttu-id="286e1-135">已部署 Microsoft Exchange 的兩個要素驗證的客戶，可能會發現 Lync 用戶端中的某些功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="286e1-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="286e1-136">這是目前的設計，因為 Lync 用戶端不支援依存于 Exchange 整合的功能的兩個要素驗證。</span><span class="sxs-lookup"><span data-stu-id="286e1-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="286e1-137">Lync 連絡人</span><span class="sxs-lookup"><span data-stu-id="286e1-137">Lync Contacts</span></span>

<span data-ttu-id="286e1-138">設定為使用整合連絡人存放區功能的 Lync 使用者，會發現在使用雙因素驗證來登入後，他們的連絡人已不再可用。</span><span class="sxs-lookup"><span data-stu-id="286e1-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="286e1-139">您應該使用 **Invoke-CsUcsRollback** 指令程式，從整合連絡人存放區中移除現有的使用者連絡人，並將其儲存在 Lync Server 2013 中，再啟用兩個要素驗證。</span><span class="sxs-lookup"><span data-stu-id="286e1-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="286e1-140">技能搜尋</span><span class="sxs-lookup"><span data-stu-id="286e1-140">Skill Search</span></span>

<span data-ttu-id="286e1-141">在 Lync 環境中已設定技能搜尋功能的客戶，會發現啟用了雙因素驗證的 Lync 時，此功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="286e1-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="286e1-142">這是設計，因為 Microsoft SharePoint 目前不支援雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="286e1-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="286e1-143">Lync 認證</span><span class="sxs-lookup"><span data-stu-id="286e1-143">Lync Credentials</span></span>

<span data-ttu-id="286e1-144">有許多與儲存的 Lync 認證相關的部署考慮，可能會影響設定為使用雙因素驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="286e1-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="286e1-145">刪除儲存的認證</span><span class="sxs-lookup"><span data-stu-id="286e1-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="286e1-146">桌面用戶端使用者應使用 Lync 用戶端中的 [ **刪除我的登入資訊** ] 選項，並從% localappdata% Microsoft Office 15.0 Lync 刪除其 SIP 設定檔資料夾， \\ \\ \\ \\ 然後再嘗試使用雙因素驗證進行第一次簽署。</span><span class="sxs-lookup"><span data-stu-id="286e1-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="286e1-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="286e1-147">DisableNTCredentials</span></span>

<span data-ttu-id="286e1-148">使用 Kerberos 或 NTLM 驗證方法時，會自動使用使用者的 Windows 認證進行驗證。</span><span class="sxs-lookup"><span data-stu-id="286e1-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="286e1-149">在一般的 Lync Server 2013 部署中啟用 Kerberos 和/或 NTLM 進行驗證時，使用者在每次登入時都不應輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="286e1-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="286e1-150">如果在提示使用者輸入 PIN 碼之前，無意提示使用者輸入其 PIN 碼，則可能會在用戶端電腦上無意間設定 **DisableNTCredentials** 登錄機碼（可能是透過「群組原則」）。</span><span class="sxs-lookup"><span data-stu-id="286e1-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="286e1-151">若要防止其他提示輸入認證，請在本機工作站上建立下列登錄專案，或使用 Lync 系統管理範本，套用至使用群組原則的指定集區的所有使用者：</span><span class="sxs-lookup"><span data-stu-id="286e1-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="286e1-152">HKEY \_ 本機 \_ 電腦 \\ 軟體 \\ 原則 \\ Microsoft \\ Office \\ 15.0 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="286e1-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="286e1-153">REG \_ DWORD： DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="286e1-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="286e1-154">值：0x0</span><span class="sxs-lookup"><span data-stu-id="286e1-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="286e1-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="286e1-155">SavePassword</span></span>

<span data-ttu-id="286e1-156">當使用者第一次登入 Lync 時，系統會提示使用者儲存其密碼。</span><span class="sxs-lookup"><span data-stu-id="286e1-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="286e1-157">如果選取此選項，則會允許將使用者的用戶端憑證儲存在個人憑證存放區，並將使用者的 Windows 認證儲存在本機電腦的認證管理員中。</span><span class="sxs-lookup"><span data-stu-id="286e1-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="286e1-158">當 Lync 設定為支援雙因素驗證時，應停用 **SavePassword** 登錄設定。</span><span class="sxs-lookup"><span data-stu-id="286e1-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="286e1-159">若要防止使用者儲存其密碼，請變更本機工作站上的下列登錄專案，或使用 Lync 系統管理範本，將其套用至指定集區的所有使用者使用群組原則：</span><span class="sxs-lookup"><span data-stu-id="286e1-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="286e1-160">HKEY \_ 目前的 \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="286e1-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="286e1-161">REG \_ DWORD： SavePassword</span><span class="sxs-lookup"><span data-stu-id="286e1-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="286e1-162">值：0x0</span><span class="sxs-lookup"><span data-stu-id="286e1-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="286e1-163">AD FS 2.0 權杖重新播放</span><span class="sxs-lookup"><span data-stu-id="286e1-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="286e1-164">AD FS 2.0 提供的功能稱為「權杖重新顯示偵測」，可以偵測出使用相同權杖的多個權杖要求，然後再將其丟棄。</span><span class="sxs-lookup"><span data-stu-id="286e1-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="286e1-165">啟用此功能時，權杖重新顯示偵測會在 WS-Federation 被動式設定檔和 SAML WebSSO 設定檔中保護驗證要求的完整性，請確定永遠不會使用相同的權杖。</span><span class="sxs-lookup"><span data-stu-id="286e1-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="286e1-166">在安全性非常重要的情況下，例如使用亭時，應啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="286e1-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="286e1-167">如需權杖重新顯示偵測的相關資訊，請參閱安全規劃及部署 AD FS 2.0 的最佳作法 [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) 。</span><span class="sxs-lookup"><span data-stu-id="286e1-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="286e1-168">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="286e1-168">External User Access</span></span>

<span data-ttu-id="286e1-169">若要將 AD FS Proxy 或反向 Proxy 設定為支援來自外部網路的 Lync 雙因素驗證，這些主題並未涵蓋這些主題。</span><span class="sxs-lookup"><span data-stu-id="286e1-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

