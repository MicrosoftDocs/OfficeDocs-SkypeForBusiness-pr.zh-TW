---
title: 針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證
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
description: 摘要：針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證。
ms.openlocfilehash: ed82e72c04d6fca0702a37819778d880b45ef617
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818835"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="8b551-103">針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="8b551-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="8b551-104">**摘要：** 針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="8b551-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="8b551-105">在混合式設定中，您的一些使用者是駐留在內部部署的商務用 Skype Server，而其他使用者則是駐留在 Office 365 版的商務用 Skype Server 上。</span><span class="sxs-lookup"><span data-stu-id="8b551-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="8b551-106">若要在混合式環境中設定伺服器對伺服器的驗證，您必須先設定您內部部署的商務用 Skype 伺服器安裝，以信任 Office 365 授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="8b551-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="8b551-107">您可以執行下列商務用 Skype Server Management 命令介面腳本來執行此程式的初始步驟：</span><span class="sxs-lookup"><span data-stu-id="8b551-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="8b551-108">請記住，租使用者的領域名稱稱通常與組織名稱不同;事實上，領域名稱稱幾乎總是與租使用者識別碼相同。</span><span class="sxs-lookup"><span data-stu-id="8b551-108">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID.</span></span> <span data-ttu-id="8b551-109">因此，腳本中的第一行是用來傳回指定租使用者的 TenantId 屬性值（在此例中為 fabrikam.com），然後將該名稱指派給 $TenantId 的變數：</span><span class="sxs-lookup"><span data-stu-id="8b551-109">Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="8b551-110">若要執行此腳本，您必須已安裝商務用 Skype Online PowerShell 模組，並使用此模組連線到您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="8b551-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="8b551-111">如果您還沒有安裝這些 Cmdlet，您的腳本將會失敗，因為 CsTenant Cmdlet 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="8b551-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="8b551-112">在腳本完成之後，您必須設定商務用 Skype 伺服器與授權伺服器之間的信任關係，以及 Exchange 2013/2016 與授權伺服器之間的第二個信任關係。</span><span class="sxs-lookup"><span data-stu-id="8b551-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="8b551-113">這只能使用 Microsoft Online Services Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="8b551-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="8b551-114">如果您尚未安裝 Microsoft Online 服務 Cmdlet，您將需要使用 Cmdlet `install-module MSOnline`從 PowerShell 知識庫安裝它。</span><span class="sxs-lookup"><span data-stu-id="8b551-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="8b551-115">您可以在 Office 365 網站上找到安裝及使用 Microsoft Online Services 模組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8b551-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="8b551-116">這些指示也會告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟及同步處理。</span><span class="sxs-lookup"><span data-stu-id="8b551-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="8b551-117">在您設定 Office 365 之後，且為商務用 Skype Server 和 Exchange 2013 建立 Office 365 服務主體之後，您就必須使用這些服務主體註冊您的認證。</span><span class="sxs-lookup"><span data-stu-id="8b551-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="8b551-118">若要這樣做，您必須先取得 x.509 Base64 憑證並儲存成。CER 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b551-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="8b551-119">此憑證隨即會套用至 Office 365 服務原則。</span><span class="sxs-lookup"><span data-stu-id="8b551-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="8b551-120">取得 x.509 憑證之後，請開啟 PowerShell console，然後匯入 Microsoft Online Windows PowerShell 模組，其中包含可用於管理服務主體的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8b551-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="8b551-121">匯入模組後，請輸入下列命令，然後按 ENTER，即可連線到 Office 365：</span><span class="sxs-lookup"><span data-stu-id="8b551-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="8b551-122">按下 ENTER 後，就會出現 [認證] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8b551-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="8b551-123">在對話方塊中輸入您的 Office 365 使用者名稱和密碼，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="8b551-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="8b551-124">一旦您連線到 Office 365，您就可以執行下列命令，以傳回服務主體的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="8b551-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="8b551-125">您應該會針對所有的服務主體取得類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="8b551-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="8b551-126">下一步是匯入、編碼並指派 x.509 憑證。</span><span class="sxs-lookup"><span data-stu-id="8b551-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="8b551-127">若要匯入並編碼憑證，請使用下列 Windows PowerShell 命令，確定要指定完整的檔案路徑。CER 檔案，當您呼叫 Import 方法時：</span><span class="sxs-lookup"><span data-stu-id="8b551-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="8b551-128">在匯入並編碼憑證之後，您就可以將憑證指派給您的 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="8b551-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="8b551-129">若要這樣做，請先使用 MsolServicePrincipal，以取得商務用 Skype 伺服器與 Microsoft Exchange 服務原則的 AppPrincipalId 屬性值;AppPrincipalId 屬性的值將用來識別指派憑證的服務主體。</span><span class="sxs-lookup"><span data-stu-id="8b551-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="8b551-130">使用 AppPrincipalId 的商務用 Skype 伺服器的 [] 屬性值，請使用下列命令，將憑證指派給商務用 Skype Online 版本：</span><span class="sxs-lookup"><span data-stu-id="8b551-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="8b551-131">接著，請重複執行命令，這次是使用 Exchange 2013 的 AppPrincipalId 屬性值。</span><span class="sxs-lookup"><span data-stu-id="8b551-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="8b551-132">如果您稍後需要刪除該憑證（例如它已過期），您可以先取得證書的 KeyId，以執行此動作：</span><span class="sxs-lookup"><span data-stu-id="8b551-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="8b551-133">該命令會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="8b551-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="8b551-134">接著，您可以使用類似以下的命令來刪除證書：</span><span class="sxs-lookup"><span data-stu-id="8b551-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="8b551-135">除了指派憑證之外，您還必須設定 Exchange Online 服務主體，並將內部部署版本的商務用 Skype Server 外部 Web 服務 Url 設定為 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="8b551-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="8b551-136">您可以執行下列兩個命令來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="8b551-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="8b551-137">在下列範例中，Pool1ExternalWebFQDN.contoso.com 是商務用 Skype 伺服器池的外部 Web 服務 URL。</span><span class="sxs-lookup"><span data-stu-id="8b551-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="8b551-138">您應該重複這些步驟，以新增部署中的所有外部 Web 服務 Url。</span><span class="sxs-lookup"><span data-stu-id="8b551-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
