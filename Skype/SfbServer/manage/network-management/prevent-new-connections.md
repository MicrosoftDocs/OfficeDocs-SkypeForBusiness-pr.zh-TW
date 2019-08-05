---
title: 防止新連接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188548"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>防止伺服器維護的新連線到商務用 Skype Server


商務用 Skype 伺服器可讓您讓伺服器離線 (例如, 將軟體或硬體升級套用), 而不會對使用者造成任何服務遺失。

當您指定防止新連線或呼叫池中伺服器的選項時, 它會在您執行此選項後立即停止進行任何新的連線與通話。 這些新的連線和通話會透過池中的其他伺服器路由。 防止新連線的伺服器可讓其在現有連線中的會話繼續下去, 直到它們自然結束為止。 當所有現有的會話都已結束時, 伺服器即可離線使用。

當您禁止與前端伺服器建立新的連線時, 某些商務用 Skype Server 功能與服務會依賴 DNS 負載平衡, 以確保其正常運作。 如果您不是在該池使用 DNS 負載平衡, 在伺服器防範新連線的期間, 透過這些服務的連線可能無法重新路由到其他伺服器, 因此當伺服器離線時, 可能會打斷. 依賴 DNS 負載平衡的功能, 以確保此選項正常運作, 如下所示:

  - 值守

  - 會議公告應用程式

  - 回應群組應用程式

  - 宣告應用程式

  - 通話駐留應用程式

如需有關 DNS 負載平衡的詳細資料, 請參閱[負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。

除了針對執行商務用 Skype Server 的伺服器上的所有服務避免新的連線外, 您也可以避免個別商務用 Skype Server 服務的新連線。 例如, 在您需要套用商務用 Skype Server update (不需要整個伺服器關閉) 的情況下, 這個方法很有用。 請注意, 當您禁止連線某個服務時, 您必須選取已群組並顯示在 Windows 服務清單中的服務。 例如, 商務用 Skype Server 前端服務和用於監視的資料收集代理程式是獨立的商務用 Skype 伺服器服務, 但在 [Windows 服務] 清單中, 它們會進行整合, 並顯示為商務用 Skype Server 前端services. 您可以防止商務用 Skype Server 前端服務的新連線, 但您無法單獨避免這兩個個別基礎商務用 Skype Server 服務的新連線。

> [!IMPORTANT]
> 當您將伺服器設定為防止新連線, 然後重新開機伺服器時, 伺服器會在啟動後立即開始接受新的連線。 若要避免這種情況, 請在重新開機伺服器前, 將伺服器設定為只暫停並手動繼續。

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>避免新的商務用 Skype 伺服器連線

1.  以管理員群組的成員身分登入本機電腦。

2.  開啟 [服務] 管理單元主控台: 按一下 [**開始**], 指向 [**所有程式**], 指向 [系統**管理工具**], 然後按一下 [**服務**]。

3.  在清單中, 按兩下您要防止新連接的商務用 Skype Server Windows 服務。

4.  在 [內容] 對話方塊中的 [**服務狀態: 已啟動**] 底下, 按一下 [**暫停**]。

5.  或者, 您可以選擇 [**啟動類型**] 旁的 [**手動**], 然後按一下 [建議]。
    
    > [!IMPORTANT]
    > 當您將伺服器設定為防止新連線, 然後重新開機伺服器時, 伺服器會在啟動後立即開始接受新的連線。 若要避免這種情況, 請在重新開機伺服器前, 將伺服器設定為只暫停並手動繼續。
