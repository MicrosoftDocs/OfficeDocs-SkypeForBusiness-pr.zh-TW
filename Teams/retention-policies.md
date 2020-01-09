---
title: Microsoft 團隊中的保留原則
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 瞭解如何保留原則，以及如何在團隊中管理它們。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 73d8de57b7b47ced8217e0f7aca384f4b55b0468
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988978"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="48726-103">Microsoft 團隊中的保留原則</span><span class="sxs-lookup"><span data-stu-id="48726-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="48726-104">團隊交談預設為持續性，且預設為永久保留。</span><span class="sxs-lookup"><span data-stu-id="48726-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="48726-105">隨著保留原則的推出，系統管理員可以在 [安全性 & 合規性中心中設定保留原則（保留與刪除），以供小組聊天和頻道訊息使用。</span><span class="sxs-lookup"><span data-stu-id="48726-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="48726-106">此功能可協助組織針對特定期間保留資料，以進行合規性（亦即保留原則），或去除資料（亦即刪除原則）（如果在特定期間內被視為負債）。</span><span class="sxs-lookup"><span data-stu-id="48726-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="48726-107">團隊保留原則可確保在您刪除資料時，會從團隊服務上的所有永久資料儲存位置中移除資料。</span><span class="sxs-lookup"><span data-stu-id="48726-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="48726-108">我們還不支援保留私人通道訊息的設定。</span><span class="sxs-lookup"><span data-stu-id="48726-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="48726-109">支援在私人通道中共用的檔案保留。</span><span class="sxs-lookup"><span data-stu-id="48726-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="48726-110">若要管理團隊保留原則，請在 [**資訊管理** > **保留**] 底下的 [Office 365 安全性 & 規範中心中使用設定和 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48726-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="48726-111">團隊保留原則支援：</span><span class="sxs-lookup"><span data-stu-id="48726-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="48726-112">[保留]：將團隊資料保持在指定的持續時間內，然後執行任何動作</span><span class="sxs-lookup"><span data-stu-id="48726-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="48726-113">保留並刪除：將團隊資料保留指定工期，然後刪除</span><span class="sxs-lookup"><span data-stu-id="48726-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="48726-114">刪除：在指定的時間之後刪除團隊資料</span><span class="sxs-lookup"><span data-stu-id="48726-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="48726-115">團隊保留原則尚不支援：</span><span class="sxs-lookup"><span data-stu-id="48726-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="48726-116">[高級保留原則] 不適用於小組聊天與團隊頻道訊息位置</span><span class="sxs-lookup"><span data-stu-id="48726-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>

<span data-ttu-id="48726-117">系統管理員可以為小組私人聊天設定個別保留原則（1:1 或1：許多聊天）與團隊頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="48726-117">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="48726-118">在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。</span><span class="sxs-lookup"><span data-stu-id="48726-118">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="48726-119">在安全性 & 合規性中心（**資訊管理** > **保留**）中設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="48726-119">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="48726-120">開啟**團隊頻道訊息**與**團隊聊天**，然後定義這些位置的保留原則（也會顯示在下圖中）。</span><span class="sxs-lookup"><span data-stu-id="48726-120">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="48726-121">當您開啟 [**小組頻道] 訊息**時，您可以指定此原則適用的小組。</span><span class="sxs-lookup"><span data-stu-id="48726-121">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="48726-122">例如，對於團隊 X、Y 和 Z，系統管理員可以將刪除原則設定為1年（透過個別選取這些團隊），然後將3年刪除原則套用到其餘的團隊。</span><span class="sxs-lookup"><span data-stu-id="48726-122">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="48726-123">您可以選取特定使用者並套用唯一的保留原則，為**小組聊天**進行相同的工作。</span><span class="sxs-lookup"><span data-stu-id="48726-123">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![[小組] 資料至 [Exchange] 和 [SharePoint] 的工作流程圖表。](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="48726-125">團隊頻道訊息位置和小組聊天位置只會解決儲存在 Exchange Online 信箱（使用者和群組信箱）中的小組交談。</span><span class="sxs-lookup"><span data-stu-id="48726-125">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="48726-126">郵件會從所有相關的儲存位置（亦即信箱、基底及聊天服務）中刪除。</span><span class="sxs-lookup"><span data-stu-id="48726-126">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="48726-127">若要管理小組檔案的保留原則，這些檔案儲存在商務用 OneDrive 和 SharePoint 中，請使用其保留原則。</span><span class="sxs-lookup"><span data-stu-id="48726-127">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="48726-128">根據設計，小組檔案的刪除原則是透過 SharePoint Online 和商務用 OneDrive 位置進行設定。</span><span class="sxs-lookup"><span data-stu-id="48726-128">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="48726-129">因此，原則可能會刪除小組聊天或頻道訊息中參照的檔案，然後再刪除這些郵件。</span><span class="sxs-lookup"><span data-stu-id="48726-129">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="48726-130">在此情況下，檔案仍會顯示在小組訊息中，但如果您按一下檔案，您會收到「找不到檔案」錯誤（如果有人從 SharePoint Online 或商務用 OneDrive 手動刪除檔案，也可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="48726-130">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="48726-131">如需設定 Office 365 保留原則的詳細資訊，請閱讀[保留原則的概覽](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="48726-131">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
