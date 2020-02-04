---
title: 安裝或移除商務用 Skype Server 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: 若要安裝及啟動或停用 Skype Server 2015 元件，請使用步驟2：設定或移除 Skype Server 元件。 您必須在您要安裝或修改的電腦上以本機管理員身分登入，而且必須能夠讀取目前網域中的 Active Directory 網域服務使用者和群組。 若要開始，請按一下 [執行]。 當您這麼做時，系統會讀取集中式管理以商店為基礎的拓朴定義。 系統會根據中央管理儲存體中定義的角色來安裝及設定必要的軟體元件。 安裝完成後，請查看摘要，然後按一下 [完成]。
ms.openlocfilehash: cc500b6fb271b628726babf91eaa86ec08f07547
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700788"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="16c4f-108">安裝或移除商務用 Skype Server 元件</span><span class="sxs-lookup"><span data-stu-id="16c4f-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="16c4f-109">若要安裝及啟動或停用 Skype Server 2015 元件，請使用**步驟2：設定或移除 Skype Server 元件**。</span><span class="sxs-lookup"><span data-stu-id="16c4f-109">To install and activate, or deactivate or uninstall Skype for Business Server 2015 components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="16c4f-110">您必須在您要安裝或修改的電腦上以本機管理員身分登入，而且必須能夠讀取目前網域中的 Active Directory 網域服務使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="16c4f-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="16c4f-111">若要開始，請按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="16c4f-111">To begin, click **Run**.</span></span> <span data-ttu-id="16c4f-112">當您這麼做時，系統會讀取集中式管理以商店為基礎的拓朴定義。</span><span class="sxs-lookup"><span data-stu-id="16c4f-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="16c4f-113">系統會根據中央管理儲存體中定義的角色來安裝及設定必要的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="16c4f-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="16c4f-114">安裝完成後，請查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="16c4f-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="16c4f-115">如果您需要查看部署嚮導所建立的記錄檔，您可以在執行步驟的 Active Directory 使用者的使用者目錄中，找到已執行部署嚮導的電腦上的檔案。</span><span class="sxs-lookup"><span data-stu-id="16c4f-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="16c4f-116">例如，如果使用者是以網域 Contoso.net 的網域管理員身分登入，則記錄檔案位於： > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="16c4f-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="16c4f-117">如果您先前已在此電腦上安裝商務用 Skype Server 2015 元件，則 [部署嚮導] 會辨識這項功能，步驟2中的按鈕將會再次顯示為 [**執行**中]。</span><span class="sxs-lookup"><span data-stu-id="16c4f-117">If you have previously installed Skype for Business Server 2015 components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="16c4f-118">如此可讓您視需要不限次數地執行這項步驟，以正確設定或修改伺服器。</span><span class="sxs-lookup"><span data-stu-id="16c4f-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

