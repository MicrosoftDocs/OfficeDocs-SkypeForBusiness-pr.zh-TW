---
title: 安裝或移除商務用 Skype Server 元件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 若要安裝及啟動或停用商務用 Skype Server 元件，您可以使用步驟2：安裝或移除 Skype Server 元件。 您必須以安裝或修改之電腦上的本機系統管理員身分登入，而且必須能夠讀取目前網域中的 Active Directory 網域服務使用者和群組。 若要開始，請按一下 [執行]。 當您這麼做時，會讀取中央管理存放區型拓撲定義。 根據中央管理存放區中所定義的角色，安裝及設定必要的軟體元件。 安裝完成時，請複查摘要，然後按一下 [完成]。
ms.openlocfilehash: 8a004e17984a927d08b7c814f8a4ba435c98971e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825047"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="ae031-108">安裝或移除商務用 Skype Server 元件</span><span class="sxs-lookup"><span data-stu-id="ae031-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="ae031-109">若要安裝及啟動或停用商務用 Skype Server 元件，您可以使用 **步驟2：安裝或移除 Skype Server 元件**。</span><span class="sxs-lookup"><span data-stu-id="ae031-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="ae031-110">您必須以安裝或修改之電腦上的本機系統管理員身分登入，而且必須能夠讀取目前網域中的 Active Directory 網域服務使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="ae031-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="ae031-111">若要開始，請按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="ae031-111">To begin, click **Run**.</span></span> <span data-ttu-id="ae031-112">當您這麼做時，會讀取中央管理存放區型拓撲定義。</span><span class="sxs-lookup"><span data-stu-id="ae031-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="ae031-113">根據中央管理存放區中所定義的角色，安裝及設定必要的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="ae031-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="ae031-114">安裝完成時，請複查摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ae031-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="ae031-115">如果您需要複查部署嚮導所建立的記錄檔，您可以在執行該步驟的 Active Directory 使用者的 Users 目錄中，找到這些記錄檔的執行部署嚮導所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="ae031-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="ae031-116">例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="ae031-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae031-117">如果您先前已在此電腦上安裝商務用 Skype Server 元件，部署嚮導會辨識這種情況，而且步驟2中的按鈕會顯示為 [ **執行** 中]。</span><span class="sxs-lookup"><span data-stu-id="ae031-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="ae031-118">這可讓您視需要執行此步驟，以正確設定或修改伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae031-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

