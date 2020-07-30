---
title: AppLocker 控制原則
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何啟用 AppLocker 應用程式控制原則的小組桌面用戶端應用程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526689"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="54a63-103">Microsoft 團隊中的 AppLocker 應用程式控制原則</span><span class="sxs-lookup"><span data-stu-id="54a63-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="54a63-104">本文說明如何使用 AppLocker 應用程式控制策略來啟用團隊桌面用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="54a63-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="54a63-105">AppLocker 的用途是專門用來限制非系統管理使用者的程式及腳本執行。</span><span class="sxs-lookup"><span data-stu-id="54a63-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="54a63-106">如需有關 AppLocker 的詳細資訊和指導方針，請參閱[什麼是 applocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。</span><span class="sxs-lookup"><span data-stu-id="54a63-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="54a63-107">啟用具有 AppLocker 的小組的程式需要建立以 AppLocker 為基礎的允許清單原則。</span><span class="sxs-lookup"><span data-stu-id="54a63-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="54a63-108">原則是使用群組原則管理軟體及/或用於 AppLocker 的 Windows PowerShell Cmdlet 來建立（請參閱[AppLocker 技術參考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)以取得詳細資訊）。</span><span class="sxs-lookup"><span data-stu-id="54a63-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="54a63-109">AppLocker 原則會儲存為 XML 格式，而且可以使用任何文字或 XML 編輯器進行編輯。</span><span class="sxs-lookup"><span data-stu-id="54a63-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="54a63-110">團隊允許清單含 AppLocker</span><span class="sxs-lookup"><span data-stu-id="54a63-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="54a63-111">AppLocker 規則會組織成集合規則。</span><span class="sxs-lookup"><span data-stu-id="54a63-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="54a63-112">AppLocker 規則會套用至目標應用程式，而它們是組成 AppLocker 原則的元件。</span><span class="sxs-lookup"><span data-stu-id="54a63-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="54a63-113">為了允許團隊，我們建議您使用[publisher 條件規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)，因為所有團隊應用程式檔案都經過數位簽章。</span><span class="sxs-lookup"><span data-stu-id="54a63-113">To allow Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="54a63-114">我們不建議使用路徑規則，因為小組安裝目錄是使用者可寫入的。</span><span class="sxs-lookup"><span data-stu-id="54a63-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="54a63-115">我們也不建議使用雜湊規則，因為每次更新團隊用戶端應用程式時，都會需要更新規則。</span><span class="sxs-lookup"><span data-stu-id="54a63-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="54a63-116">由於團隊桌面可執行檔是經過數位簽章，所以發行者條件會根據其數位簽章和內嵌版本屬性來識別應用程式檔。</span><span class="sxs-lookup"><span data-stu-id="54a63-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="54a63-117">數位簽章包含建立應用程式檔案（發行者）之公司的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="54a63-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="54a63-118">從二進位資源取得的版本資訊，包括該檔案所屬的產品名稱，以及應用程式檔案的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="54a63-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="54a63-119">Publisher 條件規則範例</span><span class="sxs-lookup"><span data-stu-id="54a63-119">Example of publisher condition rules</span></span>

<span data-ttu-id="54a63-120">對於團隊用戶端應用程式（所有檔案，所有版本），請將下列專案新增至可執行檔規則 & DLL 規則：</span><span class="sxs-lookup"><span data-stu-id="54a63-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="54a63-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="54a63-121">Related topics</span></span>
<span data-ttu-id="54a63-122">[什麼是 AppLocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技術參考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="54a63-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
