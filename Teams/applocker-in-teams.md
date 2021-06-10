---
title: AppLocker 控制項策略
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
description: 瞭解如何使用 AppLocker 應用程式Teams啟用桌面用戶端應用程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120845"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="6879f-103">應用程式中的 AppLocker 應用程式控制Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6879f-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="6879f-104">本文說明如何使用 AppLocker 應用程式控制Teams啟用桌面用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="6879f-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="6879f-105">AppLocker 的使用是專為限制非系統管理使用者執行程式與腳本所設計。</span><span class="sxs-lookup"><span data-stu-id="6879f-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="6879f-106">有關 AppLocker 的資訊與指引，請參閱 [什麼是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。</span><span class="sxs-lookup"><span data-stu-id="6879f-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="6879f-107">使用 AppLocker 啟用Teams程式需要建立 AppLocker 型允許清單策略。</span><span class="sxs-lookup"><span data-stu-id="6879f-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="6879f-108">使用群組原則管理軟體和/或 AppLocker Windows PowerShell Cmdlet 的使用來建立 (請參閱[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)技術參考，以) 。</span><span class="sxs-lookup"><span data-stu-id="6879f-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="6879f-109">AppLocker 策略會以 XML 格式儲存，而且可以使用任何文字或 XML 編輯器進行編輯。</span><span class="sxs-lookup"><span data-stu-id="6879f-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="6879f-110">Teams AppLocker 允許清單</span><span class="sxs-lookup"><span data-stu-id="6879f-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="6879f-111">AppLocker 規則會整理成規則集合。</span><span class="sxs-lookup"><span data-stu-id="6879f-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="6879f-112">AppLocker 規則會適用于目標應用程式，而這些規則是構成 AppLocker 原則的元件。</span><span class="sxs-lookup"><span data-stu-id="6879f-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="6879f-113">若要允許Teams，建議您使用發行者條件規則，因為所有[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)應用程式Teams都是數位簽章。</span><span class="sxs-lookup"><span data-stu-id="6879f-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="6879f-114">我們不建議您使用路徑規則，因為Teams目錄是使用者可寫入的。</span><span class="sxs-lookup"><span data-stu-id="6879f-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="6879f-115">我們不建議使用雜湊規則，因為每次更新用戶端應用程式時，規則Teams更新。</span><span class="sxs-lookup"><span data-stu-id="6879f-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="6879f-116">由於Teams可執行檔案是數位簽章，因此發行者條件會根據應用程式的數位簽章和內嵌版本屬性來識別應用程式檔案。</span><span class="sxs-lookup"><span data-stu-id="6879f-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="6879f-117">數位簽章包含建立應用程式檔案的公司資訊， (發行者) 。</span><span class="sxs-lookup"><span data-stu-id="6879f-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="6879f-118">從二進位資源取得的版本資訊，包括檔案屬於其中一部分的產品名稱，以及應用程式檔案的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="6879f-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="6879f-119">發行者條件規則範例</span><span class="sxs-lookup"><span data-stu-id="6879f-119">Example of publisher condition rules</span></span>

<span data-ttu-id="6879f-120">針對所有Teams用戶端應用程式 (，所有版本) 在 DLL 規則中的可執行&規則：</span><span class="sxs-lookup"><span data-stu-id="6879f-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="6879f-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="6879f-121">Related topics</span></span>
<span data-ttu-id="6879f-122">[什麼是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技術參考](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="6879f-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>