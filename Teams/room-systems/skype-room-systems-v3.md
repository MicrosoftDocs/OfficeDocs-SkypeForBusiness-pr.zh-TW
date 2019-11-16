---
title: Microsoft 團隊聊天室的管理概述
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Microsoft 團隊聊天室的管理概覽。
ms.openlocfilehash: cff0b300dc6cc9f3c15e21163554571d49e6540c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675811"
---
# <a name="management-overview"></a><span data-ttu-id="74f65-103">管理概觀</span><span class="sxs-lookup"><span data-stu-id="74f65-103">Management overview</span></span>

<span data-ttu-id="74f65-104">您必須開發並執行日常維護與作業，以確保您的使用者可以使用 Microsoft 團隊聊天室系統，並提供良好的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="74f65-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="74f65-105">監視</span><span class="sxs-lookup"><span data-stu-id="74f65-105">Monitoring</span></span> 

<span data-ttu-id="74f65-106">[監視 Microsoft 團隊室系統] 是由兩個主要活動組成：</span><span class="sxs-lookup"><span data-stu-id="74f65-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="74f65-107">裝置、應用程式和週邊裝置監控</span><span class="sxs-lookup"><span data-stu-id="74f65-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="74f65-108">品質與可靠性監控（CQD）</span><span class="sxs-lookup"><span data-stu-id="74f65-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="74f65-109">Microsoft 團隊聊天室裝置、應用程式和週邊裝置監控</span><span class="sxs-lookup"><span data-stu-id="74f65-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="74f65-110">若要確保使用者能夠使用 Microsoft 團隊會議室單元，單位必須是 [開啟]，並聯機至網路，且已正確設定 Microsoft [小組聊天室] 應用程式，且已連接至正常運作的週邊裝置。</span><span class="sxs-lookup"><span data-stu-id="74f65-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="74f65-111">Microsoft [團隊聊天室] 應用程式和已連接週邊裝置狀態的相關資訊，由 Microsoft 團隊聊天室應用程式寫入 Windows 事件記錄，並在[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)中記錄。</span><span class="sxs-lookup"><span data-stu-id="74f65-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="74f65-112">**正在**</span><span class="sxs-lookup"><span data-stu-id="74f65-112">**Setting**</span></span>|<span data-ttu-id="74f65-113">**讓**</span><span class="sxs-lookup"><span data-stu-id="74f65-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74f65-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = （dword）1</span><span class="sxs-lookup"><span data-stu-id="74f65-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="74f65-115">可讓 Microsoft 團隊聊天室啟動</span><span class="sxs-lookup"><span data-stu-id="74f65-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="74f65-116">電源管理-\>在 AC 上，10分鐘後關閉螢幕</span><span class="sxs-lookup"><span data-stu-id="74f65-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="74f65-117">電源管理-\>在交流電上，請勿將系統置於睡眠狀態</span><span class="sxs-lookup"><span data-stu-id="74f65-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="74f65-118">讓 Microsoft 團隊聊天室關閉附加的顯示，並自動喚醒</span><span class="sxs-lookup"><span data-stu-id="74f65-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="74f65-119">淨帳戶/maxpwage：無限制</span><span class="sxs-lookup"><span data-stu-id="74f65-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="74f65-120">或同等的方式，在本機帳戶上停用密碼過期。</span><span class="sxs-lookup"><span data-stu-id="74f65-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="74f65-121">如果不這麼做，最終會導致 Skype 帳戶無法針對過期密碼登入。</span><span class="sxs-lookup"><span data-stu-id="74f65-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="74f65-122">請注意，這會影響電腦上的所有本機帳戶，因此無法設定這種情況，也會導致盒上的系統管理帳戶最終過期。</span><span class="sxs-lookup"><span data-stu-id="74f65-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="74f65-123">讓 Skype 帳戶永遠登入</span><span class="sxs-lookup"><span data-stu-id="74f65-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="74f65-124">使用群組原則來傳送檔案將在 [[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)] 中討論。</span><span class="sxs-lookup"><span data-stu-id="74f65-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="74f65-125">使用 PowerShell 進行遠端系統管理</span><span class="sxs-lookup"><span data-stu-id="74f65-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="74f65-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="74f65-126"></span></span>

<span data-ttu-id="74f65-127">建議您使用 Microsoft Operations Manager Suite 來監視 Microsoft 團隊聊天室系統。</span><span class="sxs-lookup"><span data-stu-id="74f65-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="74f65-128">如需有關如何設定監視及基本通知的指導方針，請參閱[使用 Azure 監視器部署 Microsoft 團隊聊天室管理](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="74f65-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="74f65-129">使用本指導方針，您可以建立一個便於使用的儀表板，以找出您的 Microsoft 團隊會議室在整個部署中的任何問題。</span><span class="sxs-lookup"><span data-stu-id="74f65-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="74f65-130">決策點</span><span class="sxs-lookup"><span data-stu-id="74f65-130">Decision points</span></span>|<ul><li><span data-ttu-id="74f65-131">確認您使用的是作業管理 Suite 來監視 Microsoft 團隊會議室部署。</span><span class="sxs-lookup"><span data-stu-id="74f65-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="74f65-132">決定您要用來傳送電子郵件通知的目標通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="74f65-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="74f65-133">後續步驟</span><span class="sxs-lookup"><span data-stu-id="74f65-133">Next steps</span></span>|<ul><li><span data-ttu-id="74f65-134">定義您的品質與可靠性監視方法。</span><span class="sxs-lookup"><span data-stu-id="74f65-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="74f65-135">品質與可靠性監控（CQD）</span><span class="sxs-lookup"><span data-stu-id="74f65-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="74f65-136">我們建議您在部署中執行持續運作品質與可靠性監視程式，以監控通話趨勢與會議品質與可靠性，找出任何需要考慮的事項，並努力解決問題。</span><span class="sxs-lookup"><span data-stu-id="74f65-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="74f65-137">當您將建築物資訊上傳到 CQD 時，您可以在每個建築物層面上調查通話品質與可靠性趨勢，這可讓您輕鬆比較建築物，並將注意力集中在特定問題上。</span><span class="sxs-lookup"><span data-stu-id="74f65-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="74f65-138">我們建議您複習並遵循 [[體驗品質檢查] 指南](https://aka.ms/qerguide)來找出品質與可靠性趨勢，並建立行動方案來解決問題。</span><span class="sxs-lookup"><span data-stu-id="74f65-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="74f65-139">更新 Microsoft 團隊會議室 OS 和 Microsoft 團隊聊天室應用程式</span><span class="sxs-lookup"><span data-stu-id="74f65-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="74f65-140">我們建議您更新 Microsoft 團隊會議室 OS 和 Microsoft 團隊聊天室應用程式，以享受產品更新與改進的好處。</span><span class="sxs-lookup"><span data-stu-id="74f65-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="74f65-141">如需詳細指導方針，請參閱[管理 Microsoft 團隊聊天室](room-systems-v2-operations.md#software-updates)。</span><span class="sxs-lookup"><span data-stu-id="74f65-141">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="74f65-142">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="74f65-142">Windows Updates</span></span>

<span data-ttu-id="74f65-143">Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版（VL）上執行，並以標準桌面接收相同的 Windows 更新與 OS 組建。</span><span class="sxs-lookup"><span data-stu-id="74f65-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="74f65-144">如需詳細資訊，請參閱[管理 Windows 更新](updates.md)。</span><span class="sxs-lookup"><span data-stu-id="74f65-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="74f65-145">疑難排解</span><span class="sxs-lookup"><span data-stu-id="74f65-145">Troubleshooting</span></span>

<span data-ttu-id="74f65-146">我們建議您按照上述章節所述，設定運營管理套件的警示，讓您的操作小組和技術人員收到任何 Microsoft 團隊聊天室問題的警告。</span><span class="sxs-lookup"><span data-stu-id="74f65-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="74f65-147">在[使用 powershell 的遠端系統管理](room-systems-v2-operations.md#remote-management-using-powershell)中，將說明您在 powershell 遠端系統管理中擁有的選項。</span><span class="sxs-lookup"><span data-stu-id="74f65-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="74f65-148">當週邊裝置中斷連線時，您可能需要依賴本機「智慧型手」或 IT 支援來調查並重新連接裝置。</span><span class="sxs-lookup"><span data-stu-id="74f65-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="74f65-149">如需疑難排解及系統管理模式的詳細資訊，請參閱[管理 Microsoft 團隊聊天室](room-systems-v2-operations.md#admin-mode-and-device-management)。</span><span class="sxs-lookup"><span data-stu-id="74f65-149">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="74f65-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="74f65-150">See also</span></span>

[<span data-ttu-id="74f65-151">Microsoft 團隊聊天室說明</span><span class="sxs-lookup"><span data-stu-id="74f65-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="74f65-152">規劃 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="74f65-152">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="74f65-153">部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="74f65-153">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="74f65-154">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="74f65-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="74f65-155">使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定</span><span class="sxs-lookup"><span data-stu-id="74f65-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
