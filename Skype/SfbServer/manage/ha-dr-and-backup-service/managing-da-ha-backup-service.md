---
title: 管理災難修復、高可用性及備份服務
ms.reviewer: null
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 深入瞭解災難修復作業的程式，以及維護備份服務，以同步處理成對前端集區中的資料。
---


# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>管理商務用 Skype Server 的嚴重損壞修復、高可用性及備份服務

本節包含嚴重損壞修復作業的程式，以及維護備份服務，以同步處理成對前端集區中的資料。

容錯移轉和回切回的嚴重損壞修復程式都是手動。 如果發生災難，系統管理員必須手動呼叫容錯移轉程式。 修復集區之後，回復器也同樣適用。

本節中的嚴重損壞修復程式假設下列各項：

  - 您的部署具有成對的前端集區，位於不同的網站，如 [規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)所述。 備份服務已在這些配對集區上執行，使其保持同步。

  - 如果中央管理存放區裝載于任何集區上，則會在兩個配對集區上安裝並執行，其中一個集區會裝載作用中的主集區，而另一個集區會主控備用的集區。

> [!IMPORTANT]
> 在下列程式中， *PoolFQDN* 參數會參照受災難影響的集區的 FQDN，而不會重新導向受影響使用者的集區。 針對相同組受影響的使用者，它會在容錯移轉和回切 (Cmdlet 中同時參考相同的集區，也就是在容錯移轉) 之前第一位使用者的集區。<BR><br>例如，假設某個案例位於集區 P1 的所有使用者都已容錯移轉至備份組區 P2。 如果系統管理員想要移動所有目前由 P2 服務服務的使用者，以 P1 為服務，系統管理員必須執行下列步驟： 
> <OL>
> <LI>
> <P>使用回復指令 Cmdlet，將原來在 P1 上的所有使用者都從 P2 重新容錯回復至 P1。 在此情況下， *PoolFQDN* 為 P1's FQDN。</P>
> <LI>
> <P>使用容錯移轉指令，將所有原先位於 P2 的使用者容錯移轉至 P1。 在此情況下，PoolFQDN 為 P2's FQDN。</P>
> <LI>
> <P>如果系統管理員稍後想要將這些 P2 使用者容錯回復回 P2，則 PoolFQDN 為 P2's FQDN。</P></LI></OL><br>請注意，必須先執行上述步驟1，再執行步驟2以保留集區完整性。 如果您在步驟1之前嘗試步驟2，則步驟 2 Cmdlet 會失敗。


## <a name="see-also"></a>另請參閱

[規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
