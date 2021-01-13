---
title: 匯入憑證 (簡介)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: 若要匯入憑證，您必須提供憑證檔案的路徑。 在 [選取憑證檔案] 文字方塊中，您可以輸入完整路徑和檔案名稱，也可以按一下 [瀏覽] 按鈕並瀏覽至路徑位置和檔案名稱 (通常是 .p7b、.pfx 或 .cer 檔案)。
ms.openlocfilehash: ec0eb1593c628e44fcbe5cfb8d47a381b9281406
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837103"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="4f932-104">匯入憑證 (簡介)</span><span class="sxs-lookup"><span data-stu-id="4f932-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="4f932-p102">若要匯入憑證，您必須提供憑證檔案的路徑。在 **[選取憑證檔案]** 文字方塊中，您可以輸入完整路徑和檔案名稱，也可以按一下 **[瀏覽]** 按鈕並瀏覽至路徑位置和檔案名稱 (通常是 .p7b、.pfx 或 .cer 檔案)。</span><span class="sxs-lookup"><span data-stu-id="4f932-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="4f932-107">如果憑證包含私密金鑰，請選取 [ **憑證檔案包含憑證的私密金鑰**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4f932-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="4f932-108">選取此核取方塊後就能輸入 **[密碼]** 文字方塊。</span><span class="sxs-lookup"><span data-stu-id="4f932-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="4f932-109">如果您的憑證有相關聯的私密金鑰，則建立憑證時通常會將密碼設在私密金鑰上。</span><span class="sxs-lookup"><span data-stu-id="4f932-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="4f932-110">您需要輸入私密金鑰的密碼，才能將憑證和私密金鑰匯入憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="4f932-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="4f932-111">提供憑證檔案路徑的資訊並 (選用) 提供所需的私密金鑰密碼之後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="4f932-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4f932-112">如果您不知道私密金鑰的密碼，匯入會失敗。</span><span class="sxs-lookup"><span data-stu-id="4f932-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

