---
title: 在商務用 Skype Server 2015 和 Exchange Server 中設定合作夥伴應用程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要：將伺服器設定為 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 的伺服器驗證。
ms.openlocfilehash: 47f192ce11a48ab4c256ac6a1f499aa24563a725
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110109"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="f9877-103">在商務用 Skype Server 和 Exchange Server 中設定合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="f9877-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="f9877-104">**摘要：** 設定伺服器對 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 的伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="f9877-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="f9877-105">伺服器對伺服器驗證通常需要兩部伺服器必須與彼此進行通訊，以及協力廠商的安全性權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="f9877-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="f9877-106">如果伺服器 A 和伺服器 B 需要通訊，則這兩部伺服器通常會先聯繫權杖伺服器，然後取得相互信任的安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="f9877-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="f9877-107">伺服器 A 接著會向伺服器 B 呈現該安全性權杖 (，反之亦然) 做為保證其真實性和可信性的方式。</span><span class="sxs-lookup"><span data-stu-id="f9877-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="f9877-108">不過，這是一般規則。</span><span class="sxs-lookup"><span data-stu-id="f9877-108">However, that's a general rule.</span></span> <span data-ttu-id="f9877-109">商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013 不需要使用協力廠商的 token 伺服器進行通訊，而是使用另一個憑證伺服器進行通訊;這是因為這些伺服器產品可以建立可以彼此接受的安全性權杖，而不需要個別的權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="f9877-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="f9877-110"> (此功能僅適用于商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f9877-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="f9877-111">如果您需要使用其他伺服器（包括其他 Microsoft server 產品）設定伺服器對伺服器的驗證，則需要使用協力廠商的 token 伺服器來執行。 ) </span><span class="sxs-lookup"><span data-stu-id="f9877-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="f9877-112">若要設定商務用 Skype Server 與 Exchange Server 之間的伺服器對伺服器驗證，您必須執行下列兩項動作： 1) 您必須將適當的憑證指派給每個伺服器;而且，2) 您必須將每一部伺服器設定為另一部伺服器的夥伴應用程式：也就是說，您必須將商務用 Skype 伺服器設定為 Exchange Server 的夥伴應用程式，而且您必須將 Exchange 伺服器設定為商務用 Skype 伺服器的夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9877-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="f9877-113">設定商務用 Skype 伺服器成為 Exchange Server 的夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="f9877-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="f9877-114">將商務用 Skype 伺服器設定為具有 Exchange server 2016 或 Exchange Server 2013 之夥伴應用程式的最簡單方法，就是執行 Configure-EnterprisePartnerApplication.ps1 腳本，該腳本是隨 Exchange Server 一起發行的 Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="f9877-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="f9877-115">若要執行這個腳本，您必須供應商務用 Skype Server 驗證元資料檔案的 URL;這通常是商務用 Skype 伺服器集區的完整功能變數名稱，後面加上尾碼/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="f9877-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="f9877-116">例如：</span><span class="sxs-lookup"><span data-stu-id="f9877-116">For example:</span></span>
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="f9877-117">若要將商務用 Skype 伺服器設定為夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似此 (的命令，假設 Exchange 已安裝在磁碟機 C：上，且其使用預設資料夾路徑) ：</span><span class="sxs-lookup"><span data-stu-id="f9877-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="f9877-118">設定夥伴應用程式之後，建議您在 Exchange 信箱和用戶端存取伺服器上停止並重新啟動網際網路資訊服務 (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="f9877-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="f9877-119">您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：</span><span class="sxs-lookup"><span data-stu-id="f9877-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="f9877-120">您可以從 Exchange 管理命令介面或任何其他命令視窗中執行此命令，在系統管理員許可權下執行。</span><span class="sxs-lookup"><span data-stu-id="f9877-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="f9877-121">將 Exchange 伺服器設定為商務用 Skype Server 的夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="f9877-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="f9877-122">將商務用 Skype 伺服器設定為 Exchange Server 2016 或 Exchange Server 2013 的夥伴應用程式之後，您必須將 Exchange 伺服器設定為商務用 Skype 伺服器的夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9877-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="f9877-123">若要使用商務用 Skype Server 管理命令介面，並指定 Exchange 的驗證元資料檔案，可完成此動作。這通常是 Exchange 自動探索服務的 URI 後接尾碼/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="f9877-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="f9877-124">例如：</span><span class="sxs-lookup"><span data-stu-id="f9877-124">For example:</span></span>
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="f9877-125">在商務用 Skype Server 中，會使用 [New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Cmdlet 來設定夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9877-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="f9877-126">除了指定中繼資料 URI 之外，您還應該將應用程式信任層級設定為 [完整]。這可讓 Exchange 同時代表該領域中的自身和任何經授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9877-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="f9877-127">例如：</span><span class="sxs-lookup"><span data-stu-id="f9877-127">For example:</span></span>
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="f9877-128">或者，您也可以複製及修改商務用 Skype Server 的伺服器對伺服器驗證檔中找到的腳本程式碼，以建立合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9877-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="f9877-129">如需詳細資訊，請參閱 [管理伺服器對伺服器驗證 (OAuth) 和商務用 Skype server 文章中的夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9877-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="f9877-130">如果您已成功設定商務用 Skype Server 和 Exchange Server 的夥伴應用程式，您也已成功設定兩種產品之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="f9877-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="f9877-131">商務用 skype 伺服器包含 Windows PowerShell Cmdlet [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) ，可讓您驗證服務器對伺服器驗證是否已正確設定，以及商務用 Skype Server Storage Service 是否可以連線至 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f9877-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="f9877-132">此 Cmdlet 的執行方式是連線至 Exchange Server 使用者的信箱、將專案寫入該使用者的 [交談記錄] 資料夾中，然後 (選擇性) 刪除該專案。</span><span class="sxs-lookup"><span data-stu-id="f9877-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="f9877-133">若要測試商務用 Skype Server 和 Exchange Server 的整合，請從商務用 Skype Server 管理命令介面執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="f9877-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="f9877-134">在上述命令中，SipUri 代表在 Exchange 伺服器上具有帳戶之使用者的 SIP 位址;您的命令將會失敗。這不是有效的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9877-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9877-135">如果您收到來自此 Cmdlet 的401回應，這可能是因為 Exchange 的預設設定不支援接受 Oauth 權杖。</span><span class="sxs-lookup"><span data-stu-id="f9877-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="f9877-136">如需在 Exchange 中使用 Oauth 的詳細資訊，請參閱 [Configure OAuth authentication with SharePoint 2013 And 商務用 Skype Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="f9877-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help).</span></span> 
  
<span data-ttu-id="f9877-137">如果測試成功且已建立連線，您就可以繼續設定選用的功能，例如封存整合和整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="f9877-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>