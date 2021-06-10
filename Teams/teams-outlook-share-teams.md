---
title: 共用至Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 瞭解共用至Teams功能，讓使用者從 Outlook 共用電子郵件和電子郵件附件至任何聊天或頻道Teams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098219"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="ecffd-103">從 Teams 共用Outlook</span><span class="sxs-lookup"><span data-stu-id="ecffd-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="ecffd-104">從 Teams 共用到Outlook (共用Teams) 讓使用者共用電子郵件 ，包括附件Outlook到任何聊天或頻道Teams。</span><span class="sxs-lookup"><span data-stu-id="ecffd-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="ecffd-105">Outlook共用至Teams</span><span class="sxs-lookup"><span data-stu-id="ecffd-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="ecffd-106">共用至Teams功能需要一個適用于 Outlook 的Outlook。</span><span class="sxs-lookup"><span data-stu-id="ecffd-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="ecffd-107">每當使用者以 Web 應用程式或桌面用戶端Teams時，系統就會自動Teams此附加元件。</span><span class="sxs-lookup"><span data-stu-id="ecffd-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="ecffd-108">請務必在[Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)的 Outlook 用戶端Exchange Online 和用戶端存取規則中檢查[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)Outlook 的附加元件。</span><span class="sxs-lookup"><span data-stu-id="ecffd-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="ecffd-109">此外，停用已連接體驗可能會防止Outlook的附加元件正常運作。</span><span class="sxs-lookup"><span data-stu-id="ecffd-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="ecffd-110">請參閱[在 Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)中連接體驗以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ecffd-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="ecffd-111">共用至Teams使用與使用者以電子郵件傳送頻道時相同的傳輸機制。</span><span class="sxs-lookup"><span data-stu-id="ecffd-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="ecffd-112">若要共用至聊天， (電子郵件附件) 電子郵件附件會複製到寄件者OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ecffd-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="ecffd-113">若要共用至頻道，電子郵件和附件會複製到 SharePoint 中的電子郵件SharePoint。</span><span class="sxs-lookup"><span data-stu-id="ecffd-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="ecffd-114">Outlook 共用至 Teams 的附加元件會使用需求集 1.7，如[Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)的附加元件檔所詳述，其中包含 Outlook 附加元件的詳細資料、Outlook 附加元件的環境需求，以及需求集 1.7 支援的特定 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="ecffd-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="ecffd-115">啟用或停用共用至Teams</span><span class="sxs-lookup"><span data-stu-id="ecffd-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="ecffd-116">您可以Outlook PowerShell Cmdlet 選擇性地停用或啟用共用至Teams的附加元件。</span><span class="sxs-lookup"><span data-stu-id="ecffd-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="ecffd-117">只有在安裝該附加元件之後，才能停用該附加元件。</span><span class="sxs-lookup"><span data-stu-id="ecffd-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="ecffd-118">如果您想要針對租使用者中的所有使用者強制執行停用，請定期執行腳本。</span><span class="sxs-lookup"><span data-stu-id="ecffd-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="ecffd-119">若要停用共用用來Outlook的Teams，請執行[此處找到的 Cmdlet。](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="ecffd-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="ecffd-120">若要啟用 Share 用來Outlook的Teams，請執行[此處找到的 Cmdlet。](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="ecffd-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="ecffd-121">瀏覽器和單一登入</span><span class="sxs-lookup"><span data-stu-id="ecffd-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="ecffd-122">共用至Teams，無論是網頁Outlook或桌面Outlook用戶端，都仰賴瀏覽器 WebView。</span><span class="sxs-lookup"><span data-stu-id="ecffd-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="ecffd-123">請參閱[應用程式Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)所使用的瀏覽器，以瞭解有關哪些用戶端使用特定瀏覽器的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ecffd-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ecffd-124">共用至Teams使用者瀏覽器必須同時啟用協力廠商 Cookie 和本地儲存空間存取。</span><span class="sxs-lookup"><span data-stu-id="ecffd-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="ecffd-125">共用Teams使用單一登入 (SSO) ，這表示使用者在透過共用至Teams 時不需要提供其認證。</span><span class="sxs-lookup"><span data-stu-id="ecffd-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="ecffd-126">網頁Outlook SSO 預設支援並回復 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx URL。</span><span class="sxs-lookup"><span data-stu-id="ecffd-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="ecffd-127">對於虛名網域，系統管理員必須新增適當的Azure Active Directory URL。</span><span class="sxs-lookup"><span data-stu-id="ecffd-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>