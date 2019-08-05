---
title: 管理災害復原、高可用性和備份服務
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解災害復原作業的程式, 以及維護備份服務, 這會同步處理成對的前端池中的資料。
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193586"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>管理商務用 Skype Server 災害復原、高可用性及備份服務

本節包含災害復原作業的程式, 以及維護備份服務, 以同步處理成對的前端池中的資料。

容錯移轉和回切的災害復原程式都是手動的。 如果發生災難, 系統管理員必須手動喚醒呼叫容錯移轉程式。 在修復池之後, 回切會有同樣的作用。

本節中的災難復原程式假設如下:

  - 您的部署具有成對的前端池 (位於不同的網站中), 如 [[高可用性] 和 [災害復原] 規劃](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)中所述。 備份服務已在這些成對的池中執行, 以讓它們保持同步處理。

  - 如果中央管理儲存體是裝載在任何一個 pool, 則會在兩個配對的池子上安裝並執行, 而其中一個池則是裝載作用中主機, 另一個裝載備用的池。

> [!IMPORTANT]
> 在下列程式中, *PoolFQDN*參數會參照受災難影響之池的 FQDN, 而不是重新導向受影響的使用者的池。 針對同一組受影響的使用者, 它會參照容錯移轉與回切的 Cmdlet 中的同一個池 (也就是在容錯移轉前先駐留使用者的池)。<BR><br>例如, 假設駐留在 pool P1 上的所有使用者都已容錯移轉到備份池 (P2)。 如果系統管理員想要將所有目前由 P2 提供服務的使用者移至 P1, 系統管理員必須執行下列步驟: 
> <OL>
> <LI>
> <P>使用容錯回復 Cmdlet, 將原來駐留在 P1 上的所有使用者, 從 P2 切換回 P1。 在此情況下, *PoolFQDN*是 P1's FQDN。</P>
> <LI>
> <P>使用容錯移轉 Cmdlet, 將原來駐留在 P2 上的所有使用者容錯移轉到 P1。 在此情況下, PoolFQDN 是 P2's FQDN。</P>
> <LI>
> <P>如果系統管理員稍後想要將這些 P2 使用者傳回切回 P2, PoolFQDN 是 P2's FQDN。</P></LI></OL><br>請注意, 上述步驟1必須在步驟2之前執行, 才能保留池完整性。 如果您先嘗試步驟 2, 再執行步驟 1, 則步驟 2 Cmdlet 將會失敗。


## <a name="see-also"></a>請參閱

[規劃高可用性與災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
