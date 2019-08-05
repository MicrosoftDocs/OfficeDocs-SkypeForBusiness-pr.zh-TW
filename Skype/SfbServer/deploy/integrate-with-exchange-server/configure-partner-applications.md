---
title: 在商務用 Skype Server 2015 和 Exchange Server 中設定合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '摘要: 針對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server, 將伺服器設定為伺服器驗證。'
ms.openlocfilehash: 4c7c8a0efb2432403422e33140c1a2fdf3551dd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193840"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="f6217-103">在商務用 Skype Server 和 Exchange Server 中設定合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="f6217-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="f6217-104">**摘要:** 針對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server, 將伺服器設定為伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="f6217-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="f6217-105">伺服器對伺服器驗證通常需要兩個伺服器相互通訊, 以及協力廠商安全權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6217-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="f6217-106">如果伺服器 A 和伺服器 B 需要通訊, 則這兩個伺服器通常都是透過聯繫權杖伺服器並取得相互信任的安全權杖來開始。</span><span class="sxs-lookup"><span data-stu-id="f6217-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="f6217-107">伺服器 A 接著會將該安全權杖呈現給伺服器 B (反之亦然), 以保證其真實性與可信性。</span><span class="sxs-lookup"><span data-stu-id="f6217-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="f6217-108">不過, 這是一般規則。</span><span class="sxs-lookup"><span data-stu-id="f6217-108">However, that's a general rule.</span></span> <span data-ttu-id="f6217-109">商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013 在彼此通訊時不需要使用協力廠商的權杖伺服器;這是因為這些伺服器產品可以建立一個可以彼此接受的安全權杖, 而不需要個別的權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6217-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="f6217-110">(這項功能僅適用于商務用 Skype Server、Exchange Server 2016、Exchange Server 2013 及 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f6217-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="f6217-111">如果您需要設定與其他伺服器 (包括其他 Microsoft 伺服器產品) 的伺服器對伺服器驗證, 您需要使用協力廠商的權杖伺服器來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="f6217-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="f6217-112">若要在商務用 Skype Server 與 Exchange Server 之間設定伺服器對伺服器的驗證, 您必須執行兩個動作: 1) 您必須將適當的憑證指派給每個伺服器;而且, 2) 您必須將每個伺服器設定為另一個伺服器的合作夥伴應用程式: 這表示您必須將商務用 Skype Server 設定為 Exchange Server 的合作夥伴應用程式, 而且您必須將 Exchange Server 設定為適用于 Skype 的合作夥伴應用程式商務用伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6217-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="f6217-113">將商務用 Skype 伺服器設定為 Exchange Server 的合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="f6217-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="f6217-114">若要將商務用 Skype 伺服器設定為使用 Exchange Server 2016 或 Exchange Server 2013 的合作夥伴應用程式, 最簡單的方法就是執行 Configure-EnterprisePartnerApplication. ps1 腳本 (即隨 Exchange Server 隨附的 Windows PowerShell 腳本)。</span><span class="sxs-lookup"><span data-stu-id="f6217-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="f6217-115">若要執行此腳本, 您必須供應商務用 Skype Server 驗證元資料檔案的 URL;這通常是商務用 Skype 伺服器池的完整功能變數名稱, 後面接著尾碼/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="f6217-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="f6217-116">例如：</span><span class="sxs-lookup"><span data-stu-id="f6217-116">For example:</span></span>
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="f6217-117">若要將商務用 Skype Server 設定為合作夥伴應用程式, 請開啟 Exchange 管理命令介面, 並執行類似這個的命令 (假設 Exchange 已安裝在磁碟機 C:, 且它使用預設的資料夾路徑):</span><span class="sxs-lookup"><span data-stu-id="f6217-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="f6217-118">在設定合作夥伴應用程式之後, 建議您在 Exchange 信箱和用戶端存取伺服器上停止並重新啟動 Internet 資訊服務 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="f6217-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="f6217-119">您可以使用類似這個的命令重新開機 IIS, 這會重新開機電腦 atl-exchange-001 的服務:</span><span class="sxs-lookup"><span data-stu-id="f6217-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="f6217-120">這個命令可以從 Exchange 管理命令介面或從任何其他命令視窗在 [管理員許可權] 下執行。</span><span class="sxs-lookup"><span data-stu-id="f6217-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="f6217-121">將 Exchange Server 設定為商務用 Skype Server 的合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="f6217-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="f6217-122">將商務用 Skype Server 設定為 Exchange Server 2016 或 Exchange Server 2013 的合作夥伴應用程式之後, 您必須將 Exchange Server 設定為適用于商務用 Skype Server 的合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="f6217-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="f6217-123">您可以使用商務用 Skype Server Management 命令介面, 並指定 Exchange 的驗證元資料檔案來完成此動作;這通常會是 Exchange 自動探索服務的 URI, 後面接著尾碼/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="f6217-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="f6217-124">例如：</span><span class="sxs-lookup"><span data-stu-id="f6217-124">For example:</span></span>
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="f6217-125">在商務用 Skype Server 中, 合作夥伴應用程式是使用[CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="f6217-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="f6217-126">除了指定中繼資料 URI 之外, 您也應該將應用程式信任等級設為 Full;這將允許 Exchange 代表其本身以及領域中的任何授權使用者。</span><span class="sxs-lookup"><span data-stu-id="f6217-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="f6217-127">例如：</span><span class="sxs-lookup"><span data-stu-id="f6217-127">For example:</span></span>
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="f6217-128">或者, 您也可以透過複製及修改商務用 Skype Server server 伺服器驗證檔中找到的腳本代碼, 來建立合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="f6217-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="f6217-129">如需詳細資訊, 請參閱在[商務用 Skype server 文章中管理伺服器與伺服器驗證 (OAuth) 和合作夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f6217-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="f6217-130">如果您已成功設定商務用 Skype Server 與 Exchange Server 的合作夥伴應用程式, 您也可以成功地在兩個產品之間設定伺服器對伺服器的驗證。</span><span class="sxs-lookup"><span data-stu-id="f6217-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="f6217-131">商務用 skype Server 包含 Windows PowerShell Cmdlet、[測試 CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , 可讓您確認已正確設定伺服器對伺服器驗證, 且商務用 Skype Server Storage Service 可以[連線至 Exchange Server]。</span><span class="sxs-lookup"><span data-stu-id="f6217-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="f6217-132">這個 Cmdlet 是透過連線至 Exchange 伺服器使用者的信箱、將專案寫入該使用者的 [交談記錄] 資料夾中, 然後 (選擇性) 刪除該專案來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="f6217-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="f6217-133">若要測試商務用 Skype Server 與 Exchange Server 的整合, 請從商務用 Skype Server Management Shell 執行如下的命令:</span><span class="sxs-lookup"><span data-stu-id="f6217-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="f6217-134">在上述命令中, SipUri 代表在 Exchange 伺服器上擁有帳戶的使用者的 SIP 位址;您的命令會失敗, 這不是有效的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f6217-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6217-135">如果您收到來自這個 Cmdlet 的401回應, 可能是因為 Exchange 的預設設定不包含對接受 Oauth 權杖的支援。</span><span class="sxs-lookup"><span data-stu-id="f6217-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="f6217-136">如需在 Exchange 中使用 Oauth 的詳細資訊, 請參閱[使用 SharePoint 2013 和商務用 Skype 伺服器設定 oauth 驗證](https://go.microsoft.com/fwlink/p/?LinkId=513103)。</span><span class="sxs-lookup"><span data-stu-id="f6217-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="f6217-137">如果測試成功且已建立連線, 您就可以繼續設定 [存檔整合] 和 [整合連絡人存放區] 等選用功能。</span><span class="sxs-lookup"><span data-stu-id="f6217-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
