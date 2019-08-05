---
title: 憑證精靈
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: 若要「要求」、「指派」、「移除」或「檢視」憑證，請使用「憑證精靈」。 您必須以 RTCUniversalServerAdmins 群組的成員身分登入。 若要向公用憑證授權單位 (CA) 要求憑證，您不需要任何其他群組成員資格。 若要從貴組織的公開金鑰基礎結構 (PKI) 要求憑證, 您必須確認您需要的其他人 (如果有的話)。 在要求工作期間, 您可以輸入將用來從您的 PKI 頒發 CA 申請憑證的備用認證。
ms.openlocfilehash: 0ae4a9f5bf80cc33cd743349c5353f40f2fdb986
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193356"
---
# <a name="certificate-wizard"></a><span data-ttu-id="c71c9-107">憑證精靈</span><span class="sxs-lookup"><span data-stu-id="c71c9-107">Certificate Wizard</span></span>
 
<span data-ttu-id="c71c9-108">若要「要求」\*\*\*\*、「指派」\*\*\*\*、「移除」\*\*\*\* 或「檢視」\*\*\*\* 憑證，請使用「憑證精靈」。</span><span class="sxs-lookup"><span data-stu-id="c71c9-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="c71c9-109">您必須以 RTCUniversalServerAdmins 群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="c71c9-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="c71c9-110">若要向公用憑證授權單位 (CA) 要求憑證，您不需要任何其他群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="c71c9-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="c71c9-111">若要從貴組織的公開金鑰基礎結構 (PKI) 要求憑證, 您必須確認您需要的其他人 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="c71c9-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="c71c9-112">在要求工作期間, 您可以輸入將用來從您的 PKI 頒發 CA 申請憑證的備用認證。</span><span class="sxs-lookup"><span data-stu-id="c71c9-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="c71c9-113">若要要求新的憑證，請按一下 [要求]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71c9-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="c71c9-114">若要指派尚未指派的憑證，請按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71c9-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="c71c9-115">若要移除您先前指派的憑證，請按一下 [移除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71c9-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c71c9-p103">只有當先前已指派憑證時，才能使用 [移除] \*\*\*\* 按鈕。如果 [移除] \*\*\*\* 按鈕無法使用 (呈現灰色)，表示未指派憑證。</span><span class="sxs-lookup"><span data-stu-id="c71c9-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="c71c9-118">若要檢視已指派的憑證，請按一下 [檢視]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71c9-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c71c9-p104">只有當先前已指派憑證時，才能使用 [檢視] \*\*\*\* 按鈕。如果 [檢視] \*\*\*\* 按鈕呈現灰色，表示未指派憑證。</span><span class="sxs-lookup"><span data-stu-id="c71c9-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="c71c9-121">若要重新整理目前的憑證指派畫面，請按一下 [重新整理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71c9-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="c71c9-122">若要匯入憑證存放區中不存在的憑證，請按一下 [匯入憑證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71c9-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c71c9-123">[匯入憑證] \*\*\*\* 通常可用來處理透過其他程序而非「憑證精靈」中要求所接收的憑證。</span><span class="sxs-lookup"><span data-stu-id="c71c9-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="c71c9-124">例如，PKI 系統管理員建立憑證並提供給您。</span><span class="sxs-lookup"><span data-stu-id="c71c9-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="c71c9-125">使用 [匯**入憑證**], 將憑證匯入電腦的憑證存放區, 並將它提供給商務用 Skype 伺服器加以指派。</span><span class="sxs-lookup"><span data-stu-id="c71c9-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="c71c9-p106">若要完成向組織中的 CA 要求憑證的要求程序 (需要 CA 系統管理員核准)，請按一下 [處理擱置的要求]\*\*\*\*。憑證要求會傳回擱置狀態，也會顯示擱置的要求的識別碼。若要繼續處理擱置狀態的憑證，請按一下 [重新整理]\*\*\*\*，以啟用 [處理擱置的要求] \*\*\*\* 按鈕。[處理擱置的要求] \*\*\*\* 按鈕將可供使用 (不再呈現灰色)。接著，您可以嘗試擷取擱置的要求，但在 CA 系統管理員發出或拒絕憑證之前，要求的狀態仍為擱置。如果「憑證精靈」未建立有效的擱置要求，則無法使用此按鈕。</span><span class="sxs-lookup"><span data-stu-id="c71c9-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

