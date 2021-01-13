---
title: 憑證要求 (基本)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: '[名稱和安全性設定] 頁面提供一個文字方塊，以定義好記的名稱、私密金鑰的位長度的下拉式清單，以及可讓您將憑證的私密金鑰標記為可匯出的核取方塊。'
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830413"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="e05fd-103">憑證要求 (基本)</span><span class="sxs-lookup"><span data-stu-id="e05fd-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="e05fd-104">[ **名稱和安全性設定** ] 頁面提供一個文字方塊，以定義 **好記的名稱**、私密金鑰的 **位長度** 的下拉式清單，以及可讓您將 **憑證的私密金鑰標記為可匯出** 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e05fd-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="e05fd-105">憑證上的易記 (或簡單) 名稱是易於辨識的名稱，可讓檢視憑證的人便於識別。</span><span class="sxs-lookup"><span data-stu-id="e05fd-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="e05fd-106">您可以選擇 1024、2048 或 4096 做為私密與公開金鑰組的位元長度。</span><span class="sxs-lookup"><span data-stu-id="e05fd-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="e05fd-107">選取 [將 **憑證的私密金鑰標示為可匯出** ] 核取方塊，可將憑證和私密金鑰匯出並移至另一部電腦或伺服器。</span><span class="sxs-lookup"><span data-stu-id="e05fd-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="e05fd-108">只有當您為媒體轉送驗證服務建立 Edge Server 集區時 (MRAS) 時，才需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="e05fd-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e05fd-109">若要協助維護憑證與金鑰組的安全性，您應該選取 [將憑證的私密金鑰標記為可匯出] 選項，只有在絕對必要時才。</span><span class="sxs-lookup"><span data-stu-id="e05fd-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

