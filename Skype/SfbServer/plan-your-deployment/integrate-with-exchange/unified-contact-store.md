---
title: 在商務用 Skype Server 中規劃整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: 摘要：在規劃將商務用 Skype 伺服器與 Exchange 2013 整合時，請複習本主題。
ms.openlocfilehash: fbc361dab4414ea2add286144be48b922a9d9247
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815871"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="f1644-103">在商務用 Skype Server 中規劃整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="f1644-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f1644-104">**摘要：** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請複習本主題。</span><span class="sxs-lookup"><span data-stu-id="f1644-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="f1644-105">「整合連絡人存放區」可在 Microsoft Office 產品中提供一致的連絡人體驗，讓使用者能夠在 Exchange 2013 中儲存所有連絡人資訊，但在商務用 Skype、Exchange、Outlook 中都能透過全球提供資訊以及 Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="f1644-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="f1644-106">整合連絡人存放區的需求</span><span class="sxs-lookup"><span data-stu-id="f1644-106">Requirements for unified contact store</span></span>

<span data-ttu-id="f1644-107">若要在商務用 Skype Server 中實現整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="f1644-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="f1644-108">您必須執行商務用 Skype Server 和 Exchange 2013 或2016。</span><span class="sxs-lookup"><span data-stu-id="f1644-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="f1644-109">使用者必須使用商務用 Skype 將其連絡人從商務用 Skype Server 遷移至 Exchange 2013 或2016。</span><span class="sxs-lookup"><span data-stu-id="f1644-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="f1644-110">使用者信箱必須遷移至 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="f1644-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="f1644-111">您必須在商務用 Skype Server 與 Exchange 2013 或2016之間設定伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="f1644-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f1644-112">如需在商務用 Skype Server 與 Exchange 2013 或2016之間設定驗證的詳細需求，請參閱在作業檔中[管理商務用 Skype server 中的伺服器間驗證（OAuth）與合作夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f1644-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1644-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1644-113">See also</span></span>

[<span data-ttu-id="f1644-114">在商務用 Skype Server 中部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="f1644-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
