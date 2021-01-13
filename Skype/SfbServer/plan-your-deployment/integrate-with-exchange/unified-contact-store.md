---
title: 在商務用 Skype Server 中規劃整合連絡人存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：在規劃整合商務用 Skype Server 與 Exchange 2013 時，請參閱本主題。
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816253"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="cbbce-103">在商務用 Skype Server 2015 中規劃整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="cbbce-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbbce-104">**摘要：** 在規劃整合商務用 Skype Server 與 Exchange 2013 或2016時，請參閱本主題。</span><span class="sxs-lookup"><span data-stu-id="cbbce-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="cbbce-105">整合連絡人存放區在 Microsoft Office 產品中提供一致的連絡人體驗，並讓使用者能夠在 Exchange 2013 中儲存所有聯繫資訊，但可在商務用 Skype、Exchange、Outlook 和 Outlook Web Access 之間獲得全域可用資訊。</span><span class="sxs-lookup"><span data-stu-id="cbbce-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="cbbce-106">整合連絡人存放區的需求</span><span class="sxs-lookup"><span data-stu-id="cbbce-106">Requirements for unified contact store</span></span>

<span data-ttu-id="cbbce-107">若要在商務用 Skype Server 中執行整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="cbbce-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="cbbce-108">您必須執行商務用 Skype 伺服器和 Exchange 2013 或2016。</span><span class="sxs-lookup"><span data-stu-id="cbbce-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="cbbce-109">使用者必須使用商務用 Skype 將其連絡人從商務用 Skype 伺服器遷移至 Exchange 2013 或2016。</span><span class="sxs-lookup"><span data-stu-id="cbbce-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="cbbce-110">使用者信箱必須遷移至 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="cbbce-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="cbbce-111">您必須在商務用 Skype Server 與 Exchange 2013 或2016之間設定伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="cbbce-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cbbce-112">如需在商務用 Skype Server 與 Exchange 2013 或2016之間設定驗證的詳細要求，請參閱 Operations 檔中的 [管理伺服器對伺服器驗證 (OAuth) 和商務用 Skype Server 中的夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md) 。</span><span class="sxs-lookup"><span data-stu-id="cbbce-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cbbce-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cbbce-113">See also</span></span>

[<span data-ttu-id="cbbce-114">在商務用 Skype Server 中部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="cbbce-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
