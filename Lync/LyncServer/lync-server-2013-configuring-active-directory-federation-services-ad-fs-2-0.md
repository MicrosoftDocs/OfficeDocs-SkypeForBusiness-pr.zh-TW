---
title: Lync Server 2013： 設定 Active Directory Federation Services (AD FS 2.0)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3a74f59bc996defcd9baee9162d034ab2178eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="4799b-102">設定 Lync Server 2013 的 Active Directory Federation Services (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="4799b-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4799b-103">_**上次修改主題：** 2013年-07-03_</span><span class="sxs-lookup"><span data-stu-id="4799b-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="4799b-104">下節說明如何設定來支援多重要素驗證的 Active Directory Federation Services (AD FS 2.0)。</span><span class="sxs-lookup"><span data-stu-id="4799b-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="4799b-105">如需如何安裝 AD FS 2.0 的詳細資訊，請參閱 AD FS 2.0 逐步及如何到輔助線， [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)。</span><span class="sxs-lookup"><span data-stu-id="4799b-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="4799b-106">當安裝 AD FS 2.0，請勿 Windows 伺服器管理員] 新增 Active Directory Federation Services 角色。</span><span class="sxs-lookup"><span data-stu-id="4799b-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="4799b-107">相反地，下載並安裝在 Active Directory Federation Services 2.0 RTW 套件<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>。</span><span class="sxs-lookup"><span data-stu-id="4799b-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="4799b-108">**若要設定 AD FS 來進行雙因素驗證**</span><span class="sxs-lookup"><span data-stu-id="4799b-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="4799b-109">登入的 AD FS 2.0 使用網域系統管理員帳戶的電腦。</span><span class="sxs-lookup"><span data-stu-id="4799b-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="4799b-110">啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4799b-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="4799b-111">從 Windows PowerShell 命令列中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4799b-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="4799b-112">建立與 Lync Server 2013 的累計更新每個 Lync Server 2013 的合作關係： 7 月 2013 Director、 Enterprise 集區和 Standard Edition 伺服器，藉由執行下列命令，將啟用被動驗證取代伺服器名稱專屬於您的部署：</span><span class="sxs-lookup"><span data-stu-id="4799b-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="4799b-113">從系統管理工具] 功能表中，啟動 AD FS 2.0 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="4799b-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="4799b-114">依序展開 [**信任關係** \> **信賴憑證者信任]**。</span><span class="sxs-lookup"><span data-stu-id="4799b-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="4799b-115">確認 Lync Server 2013 的累計更新您 Lync Server 2013 已建立的新信任： 7 月 2013 Enterprise 集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="4799b-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="4799b-116">建立和指派發行授權規則您信賴憑證者信任使用 Windows PowerShell 執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4799b-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="4799b-117">建立並指派您信賴憑證者信任使用 Windows PowerShell 執行下列命令來發行轉換規則：</span><span class="sxs-lookup"><span data-stu-id="4799b-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="4799b-118">從 AD FS 2.0 管理主控台中，在您信賴憑證者信任上按一下滑鼠右鍵，然後選取 [**編輯宣告規則**。</span><span class="sxs-lookup"><span data-stu-id="4799b-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="4799b-119">選取 [**發行授權規則**] 索引標籤，並確認已成功建立新的授權規則。</span><span class="sxs-lookup"><span data-stu-id="4799b-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="4799b-120">選取 [**發行轉換規則**] 索引標籤，並確認已成功建立新的轉換規則。</span><span class="sxs-lookup"><span data-stu-id="4799b-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

