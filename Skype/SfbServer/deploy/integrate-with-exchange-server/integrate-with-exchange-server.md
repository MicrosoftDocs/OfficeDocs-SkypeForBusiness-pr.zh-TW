---
title: 整合商務用 Skype Server 與 Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 摘要：檢查 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype 伺服器的整合步驟。
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104849"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="9608d-103">整合商務用 Skype Server 與 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9608d-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="9608d-104">**摘要：** 檢查 Exchange Server 2013 或更新版本以及商務用 Skype 伺服器的整合步驟。</span><span class="sxs-lookup"><span data-stu-id="9608d-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="9608d-105">Exchange Server 2013 （或更新版本）和商務用 Skype Server 相容，且能夠順利整合。</span><span class="sxs-lookup"><span data-stu-id="9608d-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="9608d-106">例如，您可以在 Microsoft Outlook 中報告商務用 Skype 使用者目前狀態資訊。同樣地，商務用 Skype 可以存取使用者的 Outlook 行事曆，請注意使用者已排程會議，並在會議期間顯示使用者目前狀態為忙碌。</span><span class="sxs-lookup"><span data-stu-id="9608d-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="9608d-107">雖然您不需要執行 Exchange 伺服器以執行商務用 Skype Server (或反過來) 這兩種產品同時增強使用者的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="9608d-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="9608d-108">本檔提供整合商務用 Skype Server 和 Exchange Server 2016 或 Exchange Server 2013 的資訊，但假設這兩種產品的初始設定和設定已經發生。</span><span class="sxs-lookup"><span data-stu-id="9608d-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="9608d-109">如需部署商務用 Skype 伺服器的詳細資訊，請參閱 [商務用 Skype Server 技術中心](../../../Hub/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="9608d-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="9608d-110">如需部署 Exchange 伺服器的詳細資訊，請參閱 Exchange 版本的部署檔。</span><span class="sxs-lookup"><span data-stu-id="9608d-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="9608d-111">如果您要將商務用 Skype 伺服器的內部部署安裝與 Microsoft Exchange Online 整合，請參閱 [設定內部部署商務用 Skype server 與 Outlook Web App 之間的整合](outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="9608d-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="9608d-112">如果您要在內部部署與 Exchange Server 進行商務用 Skype Online 整合，請參閱 [Configure OAuth 商務用 Skype online 和 exchange 內部部署](oauth-with-online-and-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="9608d-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9608d-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="9608d-113">In this section</span></span>

[<span data-ttu-id="9608d-114">在商務用 Skype Server 和 Exchange Server 中設定合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="9608d-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="9608d-115">設定商務用 Skype Server 以使用 Exchange Server 封存</span><span class="sxs-lookup"><span data-stu-id="9608d-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="9608d-116">設定 SharePoint 伺服器以搜尋已封存的商務用 Skype 資料</span><span class="sxs-lookup"><span data-stu-id="9608d-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="9608d-117">設定商務用 Skype 伺服器以使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="9608d-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="9608d-118">在商務用 Skype Server 中設定高解析度相片的使用</span><span class="sxs-lookup"><span data-stu-id="9608d-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="9608d-119">為商務用 Skype Server 語音信箱設定 Exchange Server 整合通訊</span><span class="sxs-lookup"><span data-stu-id="9608d-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="9608d-120">[整合商務用 Skype Server 和 Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="9608d-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="9608d-121">在用戶端電腦上設定個人連絡人存放區以供商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="9608d-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="9608d-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9608d-122">See also</span></span>

[<span data-ttu-id="9608d-123">規劃整合商務用 Skype 和 Exchange</span><span class="sxs-lookup"><span data-stu-id="9608d-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)