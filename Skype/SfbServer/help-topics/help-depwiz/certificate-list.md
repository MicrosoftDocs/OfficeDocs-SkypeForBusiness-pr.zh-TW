---
title: 憑證清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: 若要指派憑證，請從本機憑證儲存區選取憑證。 按 [下一步] 繼續。
ms.openlocfilehash: b63117ceb0c9caa896ba39adf7b44e1e764d1817
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827373"
---
# <a name="certificate-list"></a><span data-ttu-id="9027f-104">憑證清單</span><span class="sxs-lookup"><span data-stu-id="9027f-104">Certificate List</span></span>
 
<span data-ttu-id="9027f-105">若要指派憑證，請從本機憑證儲存區選取憑證。</span><span class="sxs-lookup"><span data-stu-id="9027f-105">To assign a certificate, select a certificate from the local certificate store.</span></span> <span data-ttu-id="9027f-106">按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="9027f-106">Click **Next** to continue.</span></span>
  
<span data-ttu-id="9027f-107">在 [ **從本機憑證儲存區選取憑證** ] 窗格中，可供選取的憑證是可指派給您所需之憑證使用方式的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="9027f-107">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need.</span></span> <span data-ttu-id="9027f-108">您可以按一下 [ **查看憑證詳細資料** ] 按鈕，確認您選取的憑證正確無誤。</span><span class="sxs-lookup"><span data-stu-id="9027f-108">You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button.</span></span> <span data-ttu-id="9027f-109">在 [ **詳細資料** ] 索引標籤上，您可以查看憑證上所設定的主體名稱和主體備選項。</span><span class="sxs-lookup"><span data-stu-id="9027f-109">On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9027f-110">您可能不會在選取窗格中列出任何憑證。</span><span class="sxs-lookup"><span data-stu-id="9027f-110">It is possible that no certificate will be listed in the selection pane.</span></span> <span data-ttu-id="9027f-111">發生這種情況時，一般原因是不會在預定的伺服器上安裝受信任的憑證授權單位憑證或中級憑證授權單位憑證，以驗證憑證，進而保證憑證所建立的信任鏈可供憑證授權單位單位使用。</span><span class="sxs-lookup"><span data-stu-id="9027f-111">When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority.</span></span> <span data-ttu-id="9027f-112">若要解決此問題，請要求並匯入憑證鏈，該憑證鏈通常包含根憑證授權單位單位 (CA) 憑證和任何中間 CA 憑證，以及發行 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="9027f-112">To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

