---
title: 下載並安裝商務用 Skype Online 連接器模組
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 下載、安裝及使用商務用 Skype Online 連接器，以建立連線至商務用 Skype Online 的遠端 Windows PowerShell 會話。
ms.openlocfilehash: 8e9441e152314fafdee8fe8292d0b62a1b17d6da
ms.sourcegitcommit: 5bcc25fb20ed72bac02bc78e40b591e67eb58686
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2020
ms.locfileid: "46564772"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="777fd-103">下載並安裝商務用 Skype Online 連接器模組</span><span class="sxs-lookup"><span data-stu-id="777fd-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="777fd-104">最新的[團隊 powershell 公開預覽版](https://www.powershellgallery.com/packages/MicrosoftTeams/)已與商務用 Skype Online 連接器整合，提供單一模組供團隊 PowerShell 管理使用。</span><span class="sxs-lookup"><span data-stu-id="777fd-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="777fd-105">商務用 Skype Online 連接器模組包含**新的 CsOnlineSession** Cmdlet，可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="777fd-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="777fd-106">此模組只受64位電腦支援 (請參閱[使用 Windows PowerShell 設定商務用 Skype Online 管理電腦](set-up-your-computer-for-windows-powershell.md)：如需詳細資訊) ，可以從 Microsoft 下載中心下載 [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) 。</span><span class="sxs-lookup"><span data-stu-id="777fd-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="777fd-107">下載 SkypeOnlinePowershell.exe 檔案，然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="777fd-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="777fd-108">按兩下**SkypeOnlinePowershell.exe**檔案。</span><span class="sxs-lookup"><span data-stu-id="777fd-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="777fd-109">在商務用 Skype Online 的 Windows PowerShell 設定向導中，選取 [ **Microsoft 軟體授權條款**] 頁面上的 [**我接受授權合約中的條款**]，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="777fd-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="777fd-110">如果出現 [**使用者帳戶控制**] 對話方塊，請按一下 **[是]** 以繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="777fd-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="777fd-111">在 [**已完成商務用 Skype Online，Windows PowerShell 模組**] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="777fd-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="777fd-112">安裝程式會將商務用 Skype Online 連接器模組 (，並將**新的-CsOnlineSession** Cmdlet) 到您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="777fd-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="777fd-113">若要存取模組，請在 [管理員認證] 底下啟動 Windows PowerShell 會話，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="777fd-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="777fd-114">如果您不想在每次啟動 Windows PowerShell 時都輸入這個命令，您可以將命令新增至您的 Windows PowerShell 設定檔。</span><span class="sxs-lookup"><span data-stu-id="777fd-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="777fd-115">若要執行此動作，請在 Windows PowerShell 提示中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="777fd-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="777fd-116">當 [記事本] 出現時，如果有任何) ，請將下列行新增到設定檔中已存在的命令底部 (：</span><span class="sxs-lookup"><span data-stu-id="777fd-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="777fd-117">儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="777fd-117">Save the file.</span></span> <span data-ttu-id="777fd-118">下次啟動 Windows PowerShell 時，系統會自動匯入商務用 Skype Online 連接器模組。</span><span class="sxs-lookup"><span data-stu-id="777fd-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="777fd-119">請注意，如果您沒有在 [管理員認證] 下執行 Windows PowerShell，就會收到錯誤訊息，且不會載入模組。</span><span class="sxs-lookup"><span data-stu-id="777fd-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="777fd-120">除了安裝商務用 Skype Online 連接器模組之外，SkypeOnlinePowershell.exe 也會安裝其他三個元件： 1) 身分識別服務用戶端執行時間程式庫 (IDCRL) ，用來處理商務用 Skype Online 的用戶端驗證;2) .NET Framework 4.5;而且，3) Microsoft Visual c + + 2012 可再發行 (x64) 套件 (版本 11.0.50727) 。</span><span class="sxs-lookup"><span data-stu-id="777fd-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="777fd-121">.NET Framework 4.5 提供用來建立及執行 .NET 應用程式的基礎結構，包括 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="777fd-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="777fd-122">Visual c + + 可再發行套件會針對沒有安裝 Microsoft Visual Studio 2012 的電腦安裝 Visual c + + 執行時間元件。</span><span class="sxs-lookup"><span data-stu-id="777fd-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="777fd-123">若要確認您電腦上目前安裝的連接器模組版本號碼，請開啟 [控制台]，開啟 [**程式和功能**]，然後檢查**商務用 Skype Online、Windows PowerShell 模組**的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="777fd-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="777fd-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="777fd-124">Related topics</span></span>
[<span data-ttu-id="777fd-125">使用 Windows PowerShell 設定商務用 skype online 管理電腦</span><span class="sxs-lookup"><span data-stu-id="777fd-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
