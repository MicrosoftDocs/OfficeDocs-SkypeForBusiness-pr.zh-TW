---
title: 憑證要求 (已傳回)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: '[線上憑證要求狀態] 頁面提供成功建立併發出線上憑證要求所產生的重要資訊。 此頁面提供可唯一識別憑證的憑證指紋。 根據預設，會選取 [將此憑證指派給商務用 Skype Server 認證用途] 核取方塊。 如果您按一下 [完成]，就會自動將憑證指派給 Lync Server 2013，目的是您在證書要求的建立步驟期間定義的用途。 根據預設，會指派證書的目的為：'
ms.openlocfilehash: 885de54ec8deeef1d326e39b5a35e7b08c633973
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687746"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="b212c-107">憑證要求 (已傳回)</span><span class="sxs-lookup"><span data-stu-id="b212c-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="b212c-108">[**線上憑證要求狀態**] 頁面提供成功建立併發出線上憑證要求所產生的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="b212c-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="b212c-109">此頁面提供可唯一識別憑證的憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="b212c-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="b212c-110">根據預設，會選取 [**將此憑證指派給商務用 Skype Server 認證用途**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b212c-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="b212c-111">如果您按一下 **[完成]**，就會自動將憑證指派給 Lync Server 2013，目的是您在證書要求的建立步驟期間定義的用途。</span><span class="sxs-lookup"><span data-stu-id="b212c-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="b212c-112">根據預設，會指派證書的目的為：</span><span class="sxs-lookup"><span data-stu-id="b212c-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="b212c-113">相互傳輸層安全性（MTLS）的伺服器預設值-與用戶端及其他伺服器的連線</span><span class="sxs-lookup"><span data-stu-id="b212c-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="b212c-114">Web 服務內部-用於傳輸層安全性/安全通訊端層的內部 Web 服務網站上的用戶端和伺服器連線（TLS/SSL）</span><span class="sxs-lookup"><span data-stu-id="b212c-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="b212c-115">在適用于 TLS/SSL 的外部 Web services 網站上的 Web 服務外部用戶端與伺服器連線</span><span class="sxs-lookup"><span data-stu-id="b212c-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="b212c-116">按一下 [**查看憑證詳細資料**] 以查看憑證，以確認憑證的屬性是您想要的內容，且該憑證已準備就緒，可在伺服器上使用。</span><span class="sxs-lookup"><span data-stu-id="b212c-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="b212c-117">按一下 **[完成]** 以完成線上憑證申請程式。</span><span class="sxs-lookup"><span data-stu-id="b212c-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="b212c-118">如果您已選取 [**將此憑證指派給商務用 Skype Server 認證使用**方式] 核取方塊，則會自動指派證書。</span><span class="sxs-lookup"><span data-stu-id="b212c-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="b212c-119">如果您選擇清除此核取方塊，您必須以個別步驟指派證書。</span><span class="sxs-lookup"><span data-stu-id="b212c-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b212c-120">如果頒發憑證授權單位（CA）根憑證不在電腦的根信任憑證授權單位存放區中，或如果中間 CA 憑證不在適當的存放區中，您會看到 [摘要狀態]，如下列影像所示。</span><span class="sxs-lookup"><span data-stu-id="b212c-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="b212c-121">您沒有指派憑證的選項。</span><span class="sxs-lookup"><span data-stu-id="b212c-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="b212c-122">若要完成憑證指派程式，您必須匯入頒發 CA 根憑證及任何中間 CA 憑證，然後按一下 [主要憑證] 嚮導頁面上的 [**指派**]，指派憑證。</span><span class="sxs-lookup"><span data-stu-id="b212c-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

