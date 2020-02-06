---
title: 匯入憑證 (簡介)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 若要匯入憑證，您必須提供憑證檔的路徑。 在 [選取證書檔案] 文字方塊中，您可以輸入完整路徑和檔案名，或按一下 [流覽] 按鈕，然後流覽至路徑位置及檔案名（通常是. p7b、.pfx 或 .cer 檔案）。
ms.openlocfilehash: 63420dad20e5174cb41f9fc00d63a1f7c25763a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823667"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="83a51-104">匯入憑證 (簡介)</span><span class="sxs-lookup"><span data-stu-id="83a51-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="83a51-105">若要匯入憑證，您必須提供憑證檔的路徑。</span><span class="sxs-lookup"><span data-stu-id="83a51-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="83a51-106">在 [**選取證書**檔案] 文字方塊中，您可以輸入完整路徑和檔案名，或按一下 [**流覽]** 按鈕，然後流覽至路徑位置及檔案名（通常是. p7b、.pfx 或 .cer 檔案）。</span><span class="sxs-lookup"><span data-stu-id="83a51-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="83a51-107">如果憑證包含私密金鑰，請選取 [**憑證檔案包含憑證的私人金鑰**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="83a51-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="83a51-108">選取此核取方塊之後，就會啟用**密碼**文字輸入。</span><span class="sxs-lookup"><span data-stu-id="83a51-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="83a51-109">如果您擁有與其相關聯的私密金鑰的憑證，則在建立證書時，通常會將密碼放在私密金鑰上。</span><span class="sxs-lookup"><span data-stu-id="83a51-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="83a51-110">您可以輸入私人金鑰的密碼，以允許將憑證和私密金鑰匯入到憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="83a51-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="83a51-111">當您已提供憑證檔路徑的資訊，以及選擇性地密碼（如果需要的話），請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83a51-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="83a51-112">如果您不知道私人金鑰的密碼，匯入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="83a51-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

