---
title: 移轉多個網站與集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 2019 支援多個網站和多個集區的部署。 將多個集區遷移至商務用 Skype Server 2019 的程式需要下列考慮：
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752655"
---
# <a name="migrating-multiple-sites-and-pools"></a>移轉多個網站與集區

商務用 Skype Server 2019 支援多個網站和多個集區的部署。 將多個集區遷移至商務用 Skype Server 2019 的程式需要下列考慮： 
  
1. 部署商務用 Skype Server 2019 試驗集區之後，您必須定義將要移至商務用 Skype Server 2019 集區的試驗使用者子集，以及驗證使用者功能的方法。 例如，將使用者移至試驗集區後，請確認使用者的會議原則已移至商務用 Skype Server 2019。 
    
2. 在試驗集區中部署 Edge Server 之後，您需要驗證外部使用者是否可以與商務用 Skype Server 2019 集區通訊。

3. 在商務用 Skype Server 2019 中已被取代，且無法再以商務用 Skype Server 2019 的功能使用，但仍可在共存環境中使用，但如果這些功能先前是部署于舊版環境中，則可繼續進行。 如果您想要繼續使用這些功能，您應該計畫繼續共存環境，而某些使用者仍會保留在舊版集區中。
    
4. 將同盟路由的 Edge server 轉換至試驗商務用 Skype Server 2019 Edge server 之後，您需要驗證同盟使用者是否可以與商務用 Skype Server 2019 集區通訊。
    
5. 移動所有使用者與非使用者的連絡人物件之後，您必須驗證舊版集區是否為空。
    
6. 驗證舊版集區是空的之後，即可停用該集區。 
    
    如需如何停用舊版集區和伺服器的詳細資訊，請參閱[階段8：解除委任舊版](phase-8-decommission-legacy-pools.md)集區。
    

