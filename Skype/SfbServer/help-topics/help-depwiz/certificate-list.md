---
title: 憑證清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: 若要指派憑證，請從本機憑證存放區選取憑證。 按 [下一步] 繼續。
ms.openlocfilehash: 9dc6235893c52e19ddb1b8aaad6acbb69d1df0b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687796"
---
# <a name="certificate-list"></a><span data-ttu-id="0189a-104">憑證清單</span><span class="sxs-lookup"><span data-stu-id="0189a-104">Certificate List</span></span>
 
<span data-ttu-id="0189a-p102">若要指派憑證，請從本機憑證存放區選取憑證。按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="0189a-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="0189a-p103">[從本機憑證存放區選取憑證]\*\*\*\* 窗格中可供選取的憑證，就是可指派至您需要之憑證使用方式的有效憑證。您可以按一下 [檢視憑證詳細資料]\*\*\*\* 按鈕，確認您選取的是正確的憑證。在 [詳細資料]\*\*\*\* 索引標籤上，您可以檢視憑證上設定的主體名稱和主體別名。</span><span class="sxs-lookup"><span data-stu-id="0189a-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0189a-p104">選取窗格中也可能不會列出任何憑證。發生此情況時，原因通常是所需伺服器上未安裝信任的根憑證或中繼憑證授權單位憑證，來向憑證授權單位驗證憑證，進而維護由憑證建立的信任鏈結。若要解決此問題，請要求並匯入憑證鏈結，其中通常包括根憑證授權單位 (CA) 憑證及任何中繼 CA 憑證和發行 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="0189a-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

