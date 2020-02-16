---
title: 下載並安裝 Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
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
- LIL_Placement
description: 下載、安裝並使用 Windows PowerShell 5.1 來建立連線至商務用 Skype Online 的遠端 PowerShell 會話。
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029094"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="a198a-103">下載並安裝 Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a198a-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="a198a-104">如果您使用的是 Windows 10 年度更新版或 Windows Server 2016，您應該已經有 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="a198a-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="a198a-105">這是因為此應用程式是預先預先安裝了這些作業系統。</span><span class="sxs-lookup"><span data-stu-id="a198a-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="a198a-106">若要判斷您使用的是哪個版本的 Microsoft PowerShelll，請在您的 Windows 7 或 Windows Server 2008 R2 或 windows Server 2012 電腦上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a198a-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="a198a-107">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **Windows PowerShell**]，然後按一下 [ **windows powershell**]。</span><span class="sxs-lookup"><span data-stu-id="a198a-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a198a-108">在 PowerShell 主控台中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a198a-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="a198a-109">類似下列的資訊應該會顯示在主控台視窗中：</span><span class="sxs-lookup"><span data-stu-id="a198a-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="a198a-110">如果傳回的版本號碼是5.1，則您執行的是 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="a198a-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="a198a-111">如果傳回的版本號碼不是5.1，則您必須安裝 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="a198a-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="a198a-112">您可以從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=54616)下載 Windows Management Framework 5.1 （包括 windows PowerShell 5.1）。</span><span class="sxs-lookup"><span data-stu-id="a198a-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="a198a-113">確認已安裝 Windows PowerShell 5.1 之後，您必須確認已針對執行遠端腳本將其設定為執行。</span><span class="sxs-lookup"><span data-stu-id="a198a-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="a198a-114">若要這樣做，請以系統管理員的身分啟動 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a198a-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="a198a-115">在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a198a-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="a198a-116">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **windows powershell**]，以滑鼠右鍵按一下 [ **windows powershell**]，然後按一下 [**以系統管理員**身分</span><span class="sxs-lookup"><span data-stu-id="a198a-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="a198a-117">如果出現 [**使用者帳戶控制**] 對話方塊，請按一下 [**是]** ，確認您要在 [管理員認證] 下執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a198a-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="a198a-118">如果您執行的是 Windows 8，請改為完成此程式：</span><span class="sxs-lookup"><span data-stu-id="a198a-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="a198a-119">存取快速鍵列，按一下 [**搜尋**]，然後以滑鼠右鍵按一下 [ **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="a198a-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="a198a-120">您可以在任何 Windows 8 電腦（觸控式螢幕或非觸控式螢幕）上快速存取快速鍵列，方法是按住 Windows 鍵，然後按 C。</span><span class="sxs-lookup"><span data-stu-id="a198a-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="a198a-121">在畫面底部的工具列中，按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="a198a-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="a198a-122">如果出現 [**使用者帳戶控制**] 對話方塊，請按一下 [**是]** ，確認您要在 [管理員認證] 下執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a198a-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="a198a-123">PowerShell 執行之後，您必須變更執行原則，以允許執行遠端腳本。</span><span class="sxs-lookup"><span data-stu-id="a198a-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="a198a-124">在 PowerShell 主控台中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a198a-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="a198a-125">當您執行上述命令時，您可能會收到下列錯誤訊息： >*設定-ExecutionPolicy：無法存取登錄機碼 "HKEY_LOCAL_MACHINE\\軟體\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft"。*</span><span class="sxs-lookup"><span data-stu-id="a198a-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="a198a-126">如果您不是在 [管理員認證] 下執行 PowerShell，通常會發生此錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a198a-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="a198a-127">關閉您的 PowerShell 會話，然後以系統管理員的身分開始新的會話。</span><span class="sxs-lookup"><span data-stu-id="a198a-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="a198a-128">若要確認是否已正確設定執行原則，請在 PowerShell 提示輸入以下內容，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="a198a-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="a198a-129">如果您傳回下列值，所有內容都已正確設定：</span><span class="sxs-lookup"><span data-stu-id="a198a-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="a198a-130">如果您目前未執行 Windows PowerShell 5.1，您也需要從 Microsoft 下載中心下載並安裝 Windows Management Framework 5.1。</span><span class="sxs-lookup"><span data-stu-id="a198a-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="a198a-131">這是包含 Windows PowerShell 5.1 和 Windows 遠端系統管理（WinRM）3.0 的安裝套件。</span><span class="sxs-lookup"><span data-stu-id="a198a-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="a198a-132">例如，如果您執行的是 Windows 7 SP1，且尚未更新為 Windows PowerShell 5.1，可能需要此安裝套件。</span><span class="sxs-lookup"><span data-stu-id="a198a-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="a198a-133">如果您執行的是 Windows Server 2016 或 Windows 10 周年紀念更新，就不需要安裝 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="a198a-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="a198a-134">Windows PowerShell 5.1 已預先安裝在這些作業系統上。</span><span class="sxs-lookup"><span data-stu-id="a198a-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="a198a-135">安裝 Windows Management Framework 5.1 之前：</span><span class="sxs-lookup"><span data-stu-id="a198a-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="a198a-136">請確定您已下載正確版本的安裝套件。</span><span class="sxs-lookup"><span data-stu-id="a198a-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="a198a-137">如果您執行的是64位版本的 Windows 7 SP1，請下載檔案 Win7AndW2K8R2-KB3191566-x64。</span><span class="sxs-lookup"><span data-stu-id="a198a-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="a198a-138">如果您執行的是32位版本的 Windows 7，請下載檔案 Win7-KB3191566-x86。</span><span class="sxs-lookup"><span data-stu-id="a198a-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="a198a-139">如果您在電腦上執行 Windows 7，請確認您已安裝 Windows 7 Service Pack 1。</span><span class="sxs-lookup"><span data-stu-id="a198a-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="a198a-140">如果不確定您執行的是哪個 Windows 版本，或者不確定您是否已安裝 Windows 7 Service Pack 1，請按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a198a-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="a198a-141">此資訊將會在 [系統] 對話方塊中報告。</span><span class="sxs-lookup"><span data-stu-id="a198a-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="a198a-142">若要安裝 Windows Management Framework 5.1，請完成[安裝和設定 WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)中的程式。</span><span class="sxs-lookup"><span data-stu-id="a198a-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="a198a-143">重新開機電腦之後，請確認 Windows PowerShell 可以啟動，而且該應用程式可以在 [管理認證] 下執行。</span><span class="sxs-lookup"><span data-stu-id="a198a-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="a198a-144">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="a198a-144">To do this:</span></span>
  
1. <span data-ttu-id="a198a-145">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **windows powershell**]，以滑鼠右鍵按一下 [ **windows powershell** ]，然後按一下 [**以系統管理員**</span><span class="sxs-lookup"><span data-stu-id="a198a-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="a198a-146">如果出現 [使用者帳戶控制] 對話方塊，請按一下 [**是]** ，確認您要在 [管理員認證] 下執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a198a-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="a198a-147">PowerShell 主控台出現後，您應該確認 WinRM 服務正在執行且已正確設定。</span><span class="sxs-lookup"><span data-stu-id="a198a-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="a198a-148">若要確認服務正在執行，請在 PowerShell 提示輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a198a-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="a198a-149">隨後就會在螢幕上顯示 WinRM 服務的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="a198a-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="a198a-150">如果服務狀態不等於「正在執行」，請輸入下列命令以啟動 WinRM 服務，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a198a-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="a198a-151">在服務啟動後，請執行下列命令，以確認 WinRM 使用的是基本驗證：</span><span class="sxs-lookup"><span data-stu-id="a198a-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="a198a-152">類似下列的資訊將會顯示在螢幕上：</span><span class="sxs-lookup"><span data-stu-id="a198a-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="a198a-153">如果基本驗證已設定為 true，就表示您已經準備好使用 PowerShell 連線到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="a198a-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="a198a-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="a198a-154">Related topics</span></span>
[<span data-ttu-id="a198a-155">設定 Windows PowerShell 電腦</span><span class="sxs-lookup"><span data-stu-id="a198a-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
