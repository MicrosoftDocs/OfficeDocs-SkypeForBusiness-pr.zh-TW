---
title: 移轉封存伺服器和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 如果您已在舊版環境中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，在商務用 Skype Server 2019 環境中部署這些伺服器。 不過，如果封存和監控功能對您的組織而言很重要，您應該先在您的商務用 Skype Server 2019 試驗集區中新增封存與監控，以便在遷移程式期間使用該功能。
ms.openlocfilehash: a5b839a1eb7d460a57d6adf36901c50479f203ad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596167"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>移轉封存伺服器和監控伺服器

如果您已在舊版環境中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，在商務用 Skype Server 2019 環境中部署這些伺服器。 不過，如果封存和監控功能對您的組織而言很重要，您應該先在您的商務用 Skype Server 2019 試驗集區中新增封存與監控，以便在遷移程式期間使用該功能。 
  
移轉過程中，如果您需要存封和監控功能，請記住以下注意事項：
  
- 封存資料和監控資料不會移至商務用 Skype Server 2019 部署。 解除委任舊版環境之前所備份的資料，將是舊版環境中的活動歷史。
    
- 舊版本的封存伺服器和監控伺服器只能與舊版前端集區相關聯。 在商務用 Skype Server 2019 中，封存與監控不再是伺服器角色，但已整合至商務用 Skype Server 2019 前端集區的服務。
    
- 在舊版和商務用 Skype Server 2019 部署共存的時間內，舊版本的封存伺服器和監控伺服器會收集位於舊版集區上之使用者的資料。 商務用 Skype Server 2019 中的封存及監控為位於商務用 Skype Server 2019 集區的使用者收集資料。
    
    > [!NOTE]
    > 在遷移階段，當您仍然使用舊版 Edge server 搭配新的商務用 Skype Server 2019 試驗集區時，舊版本的封存伺服器會繼續為位於舊版集區中的使用者收集資料，而在商務用 Skype Server 2019 中封存的使用者則會收集位於商務用 Skype Server 2019 集區之使用者的資料。 
  
- 如果您在商務用 Skype Server 2019 中使用協力廠商封存與監控解決方案搭配封存與監控，請諮詢您的廠商，瞭解何時以及如何將協力廠商解決方案與商務用 Skype Server 2019 整合。
    

