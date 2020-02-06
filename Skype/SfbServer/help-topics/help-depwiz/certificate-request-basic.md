---
title: 憑證要求 (基本)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: '[名稱及安全性設定] 頁面提供一個文字方塊，以定義易記名稱、私人與公開金鑰對的位長的下拉式清單，以及可讓您將證書的私密金鑰標示為可匯出的核取方塊。'
ms.openlocfilehash: 182edc086863b7fb2ffbbb67cc041434fa9df672
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823907"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="5b856-103">憑證要求 (基本)</span><span class="sxs-lookup"><span data-stu-id="5b856-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="5b856-104">[**名稱及安全性設定**] 頁面提供一個文字方塊，以定義**易記名稱**、私人與公開金鑰對的**位長**的下拉式清單，以及可讓您將**證書的私密金鑰標示為可匯出**的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5b856-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="5b856-105">憑證上的易記 (或簡單) 名稱是易於辨識的名稱，可讓檢視憑證的人便於識別。</span><span class="sxs-lookup"><span data-stu-id="5b856-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="5b856-106">您可以選擇 1024、2048 或 4096 做為私密與公開金鑰組的位元長度。</span><span class="sxs-lookup"><span data-stu-id="5b856-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="5b856-107">選取 [將**證書的私密金鑰標示為可匯出**] 核取方塊，即可將憑證和私密金鑰匯出並移動到另一部電腦或伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b856-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="5b856-108">只有當您為媒體轉送驗證服務 (MRAS) 建立 Edge Server 集區時，才會用到這項功能。</span><span class="sxs-lookup"><span data-stu-id="5b856-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5b856-109">若要協助維護憑證和金鑰組的安全性，您應該選取 [只有在絕對必要時才將證書的私密金鑰標示為可匯出] 選項。</span><span class="sxs-lookup"><span data-stu-id="5b856-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

