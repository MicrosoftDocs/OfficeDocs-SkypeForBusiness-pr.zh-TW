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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '摘要: 在規劃將商務用 Skype 伺服器與 Exchange 2013 整合時, 請複習本主題。'
ms.openlocfilehash: 4548773c382b4295ddfbfa141f18f0df8ba367ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192987"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a>在商務用 Skype Server 中規劃整合連絡人存放區
 
**摘要:** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時, 請複習本主題。
  
「整合連絡人存放區」可在 Microsoft Office 產品中提供一致的連絡人體驗, 讓使用者能夠在 Exchange 2013 中儲存所有連絡人資訊, 但在商務用 Skype、Exchange、Outlook 中都能透過全球提供資訊以及 Outlook Web Access。
  
## <a name="requirements-for-unified-contact-store"></a>整合連絡人存放區的需求

若要在商務用 Skype Server 中實現整合連絡人存放區:
  
- 您必須執行商務用 Skype Server 和 Exchange 2013 或2016。
    
- 使用者必須使用商務用 Skype 將其連絡人從商務用 Skype Server 遷移至 Exchange 2013 或2016。
    
- 使用者信箱必須遷移至 Exchange 2013。
    
- 您必須在商務用 Skype Server 與 Exchange 2013 或2016之間設定伺服器對伺服器驗證。
    
    > [!NOTE]
    > 如需在商務用 Skype Server 與 Exchange 2013 或2016之間設定驗證的詳細需求, 請參閱在作業的[商務用 Skype 伺服器中管理伺服器間驗證 (OAuth) 與合作夥伴應用程式](../../manage/authentication/server-to-server-and-partner-applications.md)。檔.
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中部署整合連絡人存放區](../../deploy/deploy-unified-contact-store.md)
