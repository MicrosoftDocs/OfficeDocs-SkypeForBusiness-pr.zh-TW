---
title: 建立前端與 Edge 的關聯
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: 每個前端集區只能有一個與其相關聯的 Edge Server 或 Edge 集區。 當您啟用網站的外部使用者存取時，您可以為遠端使用者提供支援。 您也可以啟用同盟使用者的支援，這些使用者可以包含對特定公用立即訊息 (IM) 連線提供者的支援 (例如 Windows Live) ，以及對匿名使用者的支援。
ms.openlocfilehash: f894a38fc48b1a2c6610e8d3b886fa028b2559b8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390465"
---
# <a name="associate-front-end-with-edge"></a>建立前端與 Edge 的關聯

每個前端集區只能有一個與其相關聯的 Edge Server 或 Edge 集區。 當您啟用網站的外部使用者存取時，您可以為遠端使用者提供支援。 您也可以啟用同盟使用者的支援，這些使用者可以包含對特定公用立即訊息 (IM) 連線提供者的支援 (例如 Windows Live) ，以及對匿名使用者的支援。

如果使用不超過 Edge Server 的容量，則網站上的所有集區和多個中央網站的集區可以使用同一個 Edge Server。 如需監控的詳細資訊 (包括規模調整在內)，請參閱＜規劃＞文件中的[規劃外部使用者存取](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)。 如需設計拓撲來支援外部使用者存取的詳細資訊，請參閱＜部署＞文件中的[定義您的 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。