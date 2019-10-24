---
title: 要從防病毒掃描中排除的小組檔案和資料夾
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 從一般的防病毒掃描中排除特定檔案和資料夾，以改善團隊效能。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b4a4591bf25d7ef1a5b6efb9ab83c4508e26110
ms.sourcegitcommit: bcebe833d5ff4fcd3d6246fc5ed80980c6f31d0c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639273"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="186fb-103">要從防病毒掃描中排除的小組檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="186fb-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="186fb-104">您可以防止防毒程式掃描特定小組檔案和資料夾，以改善小組部署的整體效能。</span><span class="sxs-lookup"><span data-stu-id="186fb-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="186fb-105">這將避免掃描檔案和資料夾上不需要掃描的系統資源開支。</span><span class="sxs-lookup"><span data-stu-id="186fb-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="186fb-106">當您的使用者彼此下載檔案或共用檔案時，這些檔案不會傳遞到下列區段中所列的位置。</span><span class="sxs-lookup"><span data-stu-id="186fb-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="186fb-107">您的使用者上傳、下載或共用檔案的位置，仍會由您的防毒程式定期進行掃描。</span><span class="sxs-lookup"><span data-stu-id="186fb-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="186fb-108">要新增至防病毒安全清單的檔案和資料夾</span><span class="sxs-lookup"><span data-stu-id="186fb-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="186fb-109">使用您防毒程式支援的程式，將下列檔案和資料夾新增至您的安全清單。</span><span class="sxs-lookup"><span data-stu-id="186fb-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="186fb-110">如此一來，就可以避免對這些位置進行防病毒掃描，以節省系統資源。</span><span class="sxs-lookup"><span data-stu-id="186fb-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="186fb-111">程式</span><span class="sxs-lookup"><span data-stu-id="186fb-111">Programs</span></span>

<span data-ttu-id="186fb-112">將下列團隊程式新增到您的防病毒安全清單中。</span><span class="sxs-lookup"><span data-stu-id="186fb-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="186fb-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="186fb-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="186fb-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="186fb-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="186fb-115">資料夾</span><span class="sxs-lookup"><span data-stu-id="186fb-115">Folders</span></span>

<span data-ttu-id="186fb-116">將下列團隊資料夾新增到您的防病毒安全清單中。</span><span class="sxs-lookup"><span data-stu-id="186fb-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="186fb-117">類別</span><span class="sxs-lookup"><span data-stu-id="186fb-117">Category</span></span>  |<span data-ttu-id="186fb-118">位置</span><span class="sxs-lookup"><span data-stu-id="186fb-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="186fb-119">程式檔</span><span class="sxs-lookup"><span data-stu-id="186fb-119">Program files</span></span>  |<span data-ttu-id="186fb-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="186fb-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="186fb-121">資料檔案</span><span class="sxs-lookup"><span data-stu-id="186fb-121">Data files</span></span>     |<span data-ttu-id="186fb-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="186fb-122">%appdata%\Microsoft\Teams</span></span>\|