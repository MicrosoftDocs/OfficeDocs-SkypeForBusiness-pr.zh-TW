---
title: 商務用 Skype Server 2015 應力與效能工具的常見問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 商務用 Skype 2015 壓力與效能工具常見問題 (FAQ), 適用于找出支援哪些工具設定、疑難排解工具問題, 以及闡明您在執行壓力和效能工具時可能會看到的 behaviours.
ms.openlocfilehash: 36bb3e05751bd69b747d84fa563347b29362ddd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193135"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 應力與效能工具的常見問題
 
商務用 Skype 2015 壓力與效能工具常見問題 (FAQ), 適用于找出支援哪些工具設定、疑難排解工具問題, 以及闡明您在執行壓力和效能工具時可能會看到的 behaviours.
  
 此常見問題涵蓋有關商務用 Skype Server 2015 的一些常見問題和效能工具, 並且可能會協助您解決問題及工具設定選項。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>我可以在生產中執行 LyncPerfTool 嗎？

建議您**不要**這麼做。 此工具會影響您的生產伺服器效能、安全性和最終使用者體驗。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>我是第一次登入我的使用者。 為什麼我的伺服器執行的是高負載？

使用者第一次登入時, 會在背景執行額外的作業。 因此, Microsoft SQL Server 後端伺服器的效能可能會下降。 建議您執行簡短的測試, 讓您的所有使用者都能登入, 然後重新開機用戶端, 才能開始使用工具來測量結果。 商務用 Skype 伺服器不支援每秒超過12個併發使用者登入會話, 但請注意, 您的伺服器可處理的實際數位取決於您的硬體設定, 且可能低於支援的值。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的用戶端記憶體不足! 我該怎麼做？

如果用戶端記憶體不足, 您就應該減少每個商務用 Skype Server 前端池登入的使用者數目。 如果問題持續發生, 您也可以選擇擴大前端池。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>我可以在商務用 Skype 伺服器上執行這個工具嗎？

您不應該這麼做。 此案例不受支援, 因為可能會因為二進位不相符而失敗, 也可能是因為目標是測量伺服器上的資源佔用情況。 實際執行工具會影響伺服器效能, 並使您的資料與度量無效。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我可以在虛擬伺服器或 Microsoft Hyper-v Server 2008/2012 上執行 LyncPerfTool 嗎？

是的, 您可以。
  
## <a name="what-does-mpop-mean"></a>MPOP 代表什麼意思？

MPOP 是一種簡短的方式, 說出「多個目前狀態點」。 MPOP 是要模擬使用者從多部電腦或裝置登入商務用 Skype 2015 用戶端的情況。 請注意, 在 LyncPerfTool 中, 每個端點都會使用預設設定檔。 換句話說, 設定檔不會在兩個目前狀態點之間分割。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我已開始 LyncPerfTool, 但卻沒有發生任何事。 這是怎麼回事？

檢查伺服器上的 [總工作端點] 計數器, 查看使用者是否正在連線。 如果使用者沒有連線, 請確認您的商務用 Skype Server 2015 設定。 您通常會看到的問題是因為其中一個伺服器名稱、使用者首碼或密碼不正確。 請注意, 外部用戶端應該指定存取 Proxy 與 TargetServer 值。 驗證設定檔中的埠號碼。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>我要如何確定已測量某個專案？

有 LyncPerfTool 的效能計數器可指出使用者是否要連線並執行動作, 但最簡單的方法就是要讓您以商務用 Skype 2015 用戶端登入其中一個帳戶, 並執行這些動作自己的動作。 檢查結果, 確認已採取測量。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>我已安裝 Lync Server 2010 容量規劃工具和/或 Lync Server 2013 容量規劃工具。 那好嗎？

 這些工具有互通性問題! 您必須卸載這些工具的所有舊版, 才能從商務用 Skype Server 2015 應力和效能工具中取得有效的資料。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>壓力與效能工具會設定 CAA 通話資訊伺服器拓撲嗎？

不行, 這些工具無法執行此動作。 工具只會建立使用者、連絡人及通訊群組清單, 以模擬使用者負載。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支援的使用者數目上限為何？

在測試中, 我們已建立最多80000個使用者, 以及執行的測試, 其中匯總了執行這些工具的30000使用者。 我們建議您最多120000個使用者, 雖然技術限制允許使用較高的值。 請記住, 這些值是由您環境中的伺服器和硬體所決定。
  

