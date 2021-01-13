---
title: 憑證要求 (已傳回)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 「線上憑證要求狀態」頁面會顯示因成功建立和發行線上憑證要求而產生的重要資訊。 此頁面提供可唯一識別憑證的憑證指紋。 依預設，會選取 [將此憑證指派給商務用 Skype Server 憑證使用方式] 核取方塊。 如果您按一下 [完成]，會自動將憑證指派給 Lync Server 2013，以供您在建立憑證要求的步驟期間定義的目的。 根據預設，指派憑證的用途如下：
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805143"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="e5af2-107">憑證要求 (已傳回)</span><span class="sxs-lookup"><span data-stu-id="e5af2-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="e5af2-108">「線上憑證要求狀態」頁面會顯示因成功建立和發行線上憑證要求而產生的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="e5af2-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="e5af2-109">此頁面提供可唯一識別憑證的憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="e5af2-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="e5af2-110">依預設，會選取 [ **將此憑證指派給商務用 Skype Server 憑證使用** 情況] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e5af2-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="e5af2-111">如果您按一下 **[完成]**，會自動將憑證指派給 Lync Server 2013，以供您在建立憑證要求的步驟期間定義的目的。</span><span class="sxs-lookup"><span data-stu-id="e5af2-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="e5af2-112">根據預設，指派憑證的用途如下：</span><span class="sxs-lookup"><span data-stu-id="e5af2-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="e5af2-113">對相互傳輸層安全性 (MTLS) 連線至用戶端和其他伺服器的伺服器預設值</span><span class="sxs-lookup"><span data-stu-id="e5af2-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="e5af2-114">Web 服務內部-內部 Web 服務網站上的內部用戶端和伺服器連線，用於傳輸層安全性/安全通訊端層 (TLS/SSL) </span><span class="sxs-lookup"><span data-stu-id="e5af2-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="e5af2-115">用於 TLS/SSL 的外部 Web 服務網站上的 Web 服務外部用戶端和伺服器連線</span><span class="sxs-lookup"><span data-stu-id="e5af2-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="e5af2-116">按一下 [檢視憑證詳細資料] 來檢視憑證，以確認憑證的內容符合預期，且憑證已可套用並運用在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e5af2-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="e5af2-117">按一下 [完成] 以完成線上憑證要求程序。</span><span class="sxs-lookup"><span data-stu-id="e5af2-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="e5af2-118">如果您選取 [ **將此憑證指派給商務用 Skype Server 憑證使用** 方式] 核取方塊，則會自動指派該憑證。</span><span class="sxs-lookup"><span data-stu-id="e5af2-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="e5af2-119">如果您選擇清除此核取方塊，您必須在不同步驟中指派憑證。</span><span class="sxs-lookup"><span data-stu-id="e5af2-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e5af2-120">如果憑證授權單位單位 (CA) 根憑證不在電腦的受信任的憑證授權單位單位存放區中，或中級 CA 憑證不在適當的存放區中，您將會看到摘要狀態，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="e5af2-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="e5af2-121">您沒有指派憑證的餘地。</span><span class="sxs-lookup"><span data-stu-id="e5af2-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="e5af2-122">若要完成憑證指派程序，您必須匯入簽發的 CA 的根憑證和任何中繼 CA 憑證，然後按一下 [憑證精靈] 主要頁面上的 [指派] 來指派憑證。</span><span class="sxs-lookup"><span data-stu-id="e5af2-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

