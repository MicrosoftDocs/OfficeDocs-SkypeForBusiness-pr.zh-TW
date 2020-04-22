---
title: 設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證。
ms.openlocfilehash: 191d5d2f391df73401ff27e8c71a60624e74296c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780732"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="645df-103">設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="645df-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="645df-104">**摘要：** 設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="645df-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="645df-105">在混合式設定中，您的部分使用者是駐留在內部部署商務用 Skype Server，而其他使用者則位於 Office 365 版本的商務用 Skype Server 上。</span><span class="sxs-lookup"><span data-stu-id="645df-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="645df-106">為了設定混合式環境中的伺服器對伺服器驗證，您必須先將內部部署的商務用 Skype 伺服器設定為信任 Office 365 授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="645df-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="645df-107">您可以執行下列商務用 Skype Server 管理命令介面腳本，以執行此程式的初始步驟：</span><span class="sxs-lookup"><span data-stu-id="645df-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="645df-p102">請記住，租用戶的領域名稱通常和組織名稱不同；事實上，領域名稱和租用戶 ID 幾乎相同。因此，指令碼第一行是用來為指定的租用戶傳回 TenantId 屬性值 (在這種情況下為 fabrikam.com)，接著將該名稱指派至變數 $TenantId：</span><span class="sxs-lookup"><span data-stu-id="645df-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="645df-110">若要執行此腳本，您必須已安裝商務用 Skype Online PowerShell 模組，並使用此模組連線到您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="645df-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="645df-111">若尚未安裝這些 Cmdlet，您的腳本將會失敗，因為 Get-CsTenant Cmdlet 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="645df-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="645df-112">腳本完成之後，您必須設定商務用 Skype Server 與授權伺服器之間的信任關係，以及 Exchange 2013/2016 和授權伺服器之間的第二個信任關係。</span><span class="sxs-lookup"><span data-stu-id="645df-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="645df-113">唯有使用 Microsoft Online Services Cmdlet 才能完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="645df-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="645df-114">若尚未安裝 Microsoft Online Services Cmdlet，您需要使用 Cmdlet `install-module MSOnline`從 PowerShell 存放庫進行安裝。</span><span class="sxs-lookup"><span data-stu-id="645df-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="645df-115">您可以在 Office 365 網站找到有關安裝及使用 Microsoft Online Services 模組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="645df-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="645df-116">這些說明也將告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟與同步處理。</span><span class="sxs-lookup"><span data-stu-id="645df-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="645df-117">在您設定 Office 365 之後，以及為商務用 Skype Server 和 Exchange 2013 建立 Office 365 服務主體之後，您將需要使用這些服務主體註冊您的認證。</span><span class="sxs-lookup"><span data-stu-id="645df-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="645df-118">為了達到此目的，您必須先取得 x.509 Base64 憑證另存為。CER 檔案。</span><span class="sxs-lookup"><span data-stu-id="645df-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="645df-119">接著此憑證將會套用至 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="645df-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="645df-120">當您取得 x.509 憑證之後，請開啟 PowerShell 主控台，然後匯入 Microsoft Online Windows PowerShell 模組，其中包含可用於管理服務主體的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="645df-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="645df-121">匯入模組後，請鍵入下列命令並按下 ENTER 鍵，以連線至 Office 365：</span><span class="sxs-lookup"><span data-stu-id="645df-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="645df-122">按下 ENTER 鍵後，將會出現認證對話方塊。</span><span class="sxs-lookup"><span data-stu-id="645df-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="645df-123">在對話方塊中輸入您的 Microsoft 365 或 Office 365 使用者名稱和密碼，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="645df-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="645df-124">當您連線至 Office 365 後，您就可以執行下列命令，以傳回服務主體的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="645df-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="645df-125">您能以類似的方式為所有服務主體取得資訊：</span><span class="sxs-lookup"><span data-stu-id="645df-125">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="645df-126">下一個步驟為匯入、編碼以及指派 X.509 憑證。</span><span class="sxs-lookup"><span data-stu-id="645df-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="645df-127">若要匯入和編碼憑證，請使用下列 Windows PowerShell 命令，確定指定您的完整檔案路徑。CER 檔案當您呼叫 Import 方法時：</span><span class="sxs-lookup"><span data-stu-id="645df-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="645df-128">憑證匯入且完成編碼後，接著您可以將憑證指派至 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="645df-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="645df-129">若要這麼做，請先使用 New-msolserviceprincipal，以取得商務用 Skype Server 和 Microsoft Exchange 服務主體的 AppPrincipalId 屬性值;AppPrincipalId 屬性的值將用來識別被指派憑證的服務主體。</span><span class="sxs-lookup"><span data-stu-id="645df-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="645df-130">使用適用于商務用 Skype Server 的 AppPrincipalId 屬性值，使用下列命令將憑證指派至商務用 Skype Online 版本：</span><span class="sxs-lookup"><span data-stu-id="645df-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="645df-131">然後您應該重複執行此命令，這次使用 Exchange 2013 的 AppPrincipalId 屬性值。</span><span class="sxs-lookup"><span data-stu-id="645df-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="645df-132">如果您稍後需要刪除該憑證，例如，如果憑證已過期，您可以先取回憑證的 KeyId，這樣做如下：</span><span class="sxs-lookup"><span data-stu-id="645df-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="645df-133">該指令將會以這種方式傳回資料：</span><span class="sxs-lookup"><span data-stu-id="645df-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="645df-134">接著您可以用類似這樣的命令來刪除憑證：</span><span class="sxs-lookup"><span data-stu-id="645df-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="645df-135">除了指派憑證之外，您還必須設定 Exchange Online 服務主體，並將內部部署版本的商務用 Skype Server 外部 Web 服務 URLs 當做 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="645df-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="645df-136">您可以執行下列兩個命令來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="645df-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="645df-137">在下列範例中，Pool1ExternalWebFQDN.contoso.com 是商務用 Skype 伺服器集區的外部 Web 服務 URL。</span><span class="sxs-lookup"><span data-stu-id="645df-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="645df-138">您應重複這些步驟，以在部署中新增所有外部 Web 服務 URLs。</span><span class="sxs-lookup"><span data-stu-id="645df-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
