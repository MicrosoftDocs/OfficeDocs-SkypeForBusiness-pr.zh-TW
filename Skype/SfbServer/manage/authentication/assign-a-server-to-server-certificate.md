---
title: 將伺服器對伺服器驗證憑證指派給商務用 Skype Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要：指派商務用 Skype Server 的伺服器對伺服器驗證憑證。
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828503"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="a65c1-103">將伺服器對伺服器驗證憑證指派給商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="a65c1-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="a65c1-104">**摘要：** 為商務用 Skype Server 指派伺服器對伺服器驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="a65c1-105">若要判斷伺服器對伺服器驗證憑證是否已指派給商務用 Skype Server，請從商務用 Skype Server 管理命令介面執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a65c1-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="a65c1-106">若未傳回憑證資訊，您必須指派 token 簽發者憑證，才能使用伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="a65c1-107">一般來說，任何商務用 Skype Server 憑證都可以做為 OAuthTokenIssuer 憑證。例如，您的商務用 Skype Server 預設憑證也可以做為 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="a65c1-108"> (OAUthTokenIssuer 憑證也可以是任何網頁伺服器憑證，包含 [主旨] 欄位中的 SIP 網功能變數名稱稱。 ) 伺服器對伺服器驗證所用之憑證的主要兩項需求如下： 1) 相同的憑證必須設定為所有前端伺服器上的 OAuthTokenIssuer 憑證;而且，2) 憑證必須至少是2048位。</span><span class="sxs-lookup"><span data-stu-id="a65c1-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="a65c1-109">如果您沒有可用於伺服器對伺服器驗證的憑證，您可以取得新的憑證，匯入新的憑證，然後使用該憑證進行伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="a65c1-110">在要求並取得新憑證之後，您可以登入任何一部前端伺服器，並使用與下列類似的 Windows PowerShell 命令，匯入並指派該憑證：</span><span class="sxs-lookup"><span data-stu-id="a65c1-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="a65c1-111">在上述命令中，Path 參數會代表憑證檔案的完整路徑，而 Password 參數則代表指派給憑證的密碼。</span><span class="sxs-lookup"><span data-stu-id="a65c1-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="a65c1-112">此程式應只執行一次：商務用 Skype Server 複寫服務會自動建立一組排程的工作，將憑證解密並部署至您的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="a65c1-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="a65c1-113">或者，您可以使用現有憑證做為伺服器對伺服器驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="a65c1-114"> (所述，可將預設憑證當做伺服器對伺服器驗證憑證使用。 ) 下列一對 Windows PowerShell 命令可取得預設憑證的 Thumbprint 屬性值，然後使用該值將預設憑證設為伺服器對伺服器驗證憑證：</span><span class="sxs-lookup"><span data-stu-id="a65c1-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="a65c1-115">在上述命令中，所檢索的憑證會設定為以全域伺服器對伺服器驗證憑證的形式運作;這表示憑證將會複製到並由所有前端伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="a65c1-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="a65c1-116">同樣地，此命令只會執行一次，且只能在其中一部前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="a65c1-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="a65c1-117">雖然所有前端伺服器都必須使用相同的憑證，但您不應該在每個前端伺服器上設定 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="a65c1-118">請改為設定憑證一次，然後讓商務用 Skype Server 複寫伺服器負責將該憑證複製到每個伺服器。</span><span class="sxs-lookup"><span data-stu-id="a65c1-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="a65c1-119">Set-CsCertificate Cmdlet 會採取問題的憑證，並立即設定該憑證充當目前的 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="a65c1-120"> (商務用 Skype Server 會保留兩個憑證類型的副本：目前的憑證和舊的憑證。 ) 如果您需要新的憑證立即開始充當 OAuthTokenIssuer 的憑證，則應該使用 Set-CsCertificate Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a65c1-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="a65c1-121">您也可以使用 Set-CsCertificate Cmdlet 來「推出」新的憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="a65c1-122">「滾動」憑證只是表示您將新的憑證設定為在指定的時間點成為目前的 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="a65c1-123">例如，此命令會檢索預設憑證，然後設定該憑證作為目前的 OAuthTokenIssuer 憑證，在2015年7月1日為止。</span><span class="sxs-lookup"><span data-stu-id="a65c1-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="a65c1-124">在2015年7月1日，新的憑證會設定為目前的 OAuthTokenIssuer 憑證，而 "old" OAuthTokenIssuer 憑證將設定為舊版憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="a65c1-125">如果您不想要使用 Windows PowerShell 您也可以使用憑證 MMC 主控台從一部前端伺服器匯出憑證，然後在其他所有的前端伺服器上匯入該相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="a65c1-126">如果您這麼做，請確定匯出私密金鑰和憑證本身。</span><span class="sxs-lookup"><span data-stu-id="a65c1-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a65c1-127">在此情況下，必須在每一部前端伺服器上執行該程式。</span><span class="sxs-lookup"><span data-stu-id="a65c1-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="a65c1-128">以這種方式匯出及匯入憑證時，商務用 Skype Server 不會將該憑證複製到每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="a65c1-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="a65c1-129">將憑證匯入至所有前端伺服器後，即可使用商務用 Skype Server 部署嚮導（而非 Windows PowerShell）來指派該憑證。</span><span class="sxs-lookup"><span data-stu-id="a65c1-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="a65c1-130">若要使用部署嚮導指派憑證，請在已安裝部署嚮導的電腦上完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a65c1-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="a65c1-131">依序按一下 [開始]、[所有程式]、[ **商務用 Skype 伺服器**]，然後按一下 [ **商務用 Skype 伺服器部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="a65c1-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="a65c1-132">在 [部署嚮導] 中，按一下 [ **安裝或更新商務用 Skype Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="a65c1-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="a65c1-133">在 [商務用 Skype 伺服器] 頁面上，按一下 [**步驟3：要求、安裝或指派憑證**] 底下的 [**執行**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a65c1-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="a65c1-134"> (注意：如果您已在此電腦上安裝憑證，則會將 [ **執行** ] 按鈕重新標示為 [ **執行** 中]。 ) </span><span class="sxs-lookup"><span data-stu-id="a65c1-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="a65c1-135">在 [憑證] 嚮導中，選取 **OAuthTokenIssuer** 憑證，然後按一下 [ **指派**]。</span><span class="sxs-lookup"><span data-stu-id="a65c1-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="a65c1-136">在 [憑證指派] 嚮導的 [ **憑證指派** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a65c1-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="a65c1-137">在 [ **憑證存放區** ] 頁面上，選取要用於伺服器對伺服器驗證的憑證，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a65c1-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="a65c1-138">在 [憑證指派摘要] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a65c1-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="a65c1-139">在 [執行命令] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a65c1-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="a65c1-140">關閉憑證嚮導和部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="a65c1-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

