---
title: 商務用 Skype Server 2015 壓力和效能工具的常見問題
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 商務用 Skype 2015 應力和效能工具常見問題解答 (FAQ) ，可找出支援哪些工具設定、疑難排解工具問題，並闡明當您執行壓力和效能工具時，可能會看到的 behaviours。
ms.openlocfilehash: fb81d31711b027d58b8d5b97ecd6d14f32c0fa0f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857290"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 壓力和效能工具的常見問題
 
商務用 Skype 2015 應力和效能工具常見問題解答 (FAQ) ，可找出支援哪些工具設定、疑難排解工具問題，並闡明當您執行壓力和效能工具時，可能會看到的 behaviours。
  
 此常見問題涵蓋有關商務用 Skype Server 2015 壓力和效能工具的常見問題，也可協助您進行疑難排解及工具設定選項。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>我可以在生產環境中執行 LyncPerfTool.exe 嗎？

建議您 **不要** 這麼做。 工具會影響實際執行伺服器的效能、安全性和使用者體驗。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>我是第一次登入我的使用者。 為什麼伺服器的負載很高？

使用者第一次登入時，會在後臺進行其他作業。 因此，Microsoft SQL Server 後端伺服器的效能可能會降級。 建議您執行簡短的測試，讓您在所有的使用者上登入，然後在開始使用工具測量結果之前重新開機用戶端。 商務用 Skype Server 不支援每秒超過12個同時使用者登入會話，但是請注意，您的伺服器可以處理的實際數目取決於您的硬體設定，而且可能會低於支援的值。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的用戶端記憶體不足！ 我該怎麼做？

如果用戶端記憶體不足，您應該減少每商務用 Skype Server 前端集區所登入的使用者數目。 如果問題持續發生，您也可以選擇擴充前端集區。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>我可以在商務用 Skype 伺服器上執行此工具嗎？

您不應該這麼做。 此案例不受支援，因為二進位不相符，也可能會因為目標是度量伺服器上的資源消耗。 實際執行工具會影響伺服器效能，並使您的資料和度量無效。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我可以在虛擬伺服器或 Microsoft Hyper-V 伺服器2008/2012 上執行 LyncPerfTool.exe 嗎？

是您可以。
  
## <a name="what-does-mpop-mean"></a>MPOP 的含義為何？

MPOP 是一種簡短的方式，說「多點顯示」。 MPOP 是要模擬使用者從多部機器或裝置登入商務用 Skype 2015 用戶端的案例。 請注意，在 LyncPerfTool.exe 中，每個端點都使用預設設定檔。 換句話說，設定檔不會在兩個目前狀態點間分割。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我已開始 LyncPerfTool.exe 但不會發生任何情況。 What's going on?

檢查伺服器上的作用中端點計數器總數，以查看使用者是否正在連線。 如果使用者未連接，請驗證商務用 Skype Server 2015 設定。 您所看到的問題通常是因為其中一個伺服器名稱、使用者前置詞或密碼不正確。 請注意，外部用戶端應指定 Access Proxy 和 TargetServer 值。 確認設定檔中的埠號碼。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>如何確定已度量專案？

LyncPerfTool 的效能計數器會指出使用者是否連線並執行動作，但確定行動的最簡單方式是使用商務用 Skype 2015 用戶端登入其中一個帳戶，並自行執行這些動作。 檢查結果，以確認已採取度量。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>我已安裝 Lync Server 2010 容量規劃工具和/或 Lync Server 2013 容量規劃工具。 這好嗎？

 這些工具有互通性問題！ 您必須卸載所有舊版工具，才能從商務用 Skype Server 2015 應力和效能工具取得有效的資料。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>壓力和效能工具是否會設定 CAA 的呼叫資訊伺服器拓撲？

否，工具不會這麼做。 工具只會建立使用者、連絡人及通訊群組清單，以模擬使用者負載。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支援的使用者數目上限為何？

在測試中，我們已建立最多80000個使用者，以及執行這些工具的30000使用者所執行的測試。 我們建議最多120000個使用者，但技術限制允許更高的值。 請記住，這些值取決於環境中的伺服器和硬體。
  

