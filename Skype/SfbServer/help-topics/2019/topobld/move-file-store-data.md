---
title: 在商務用 Skype Server 中將檔案存放區資料移至新的檔案存放區
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 如果您需要移除目前做為商務用 Skype Server 部署之檔案存放區的檔案伺服器，或者您需要進行其他變更，使目前的檔案存放區無法使用，您必須先建立新的共用。 接著，您必須執行下列步驟：
ms.openlocfilehash: 5fe93633c60ccd50da455b892a1e395e2a6872d8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392045"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>在商務用 Skype Server 中將檔案存放區資料移至新的檔案存放區

如果您需要移除目前做為商務用 Skype Server 部署之檔案存放區的檔案伺服器，或者您需要進行其他變更，使目前的檔案存放區無法使用，您必須先建立新的共用。 接著，您必須執行下列步驟：

1. 關閉使用您計畫要移除之檔案存放區的商務用 Skype Server 服務。

2. 在拓撲產生器中定義檔案存放區，併發布變更，讓部署使用新的檔案存放區。

3. 將資料移至新的檔案存放區。

4. 重新開機伺服器或服務。

5. （選用）移除舊的檔案共用和資料夾。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>將檔案存放區資料從一個檔案存放區移至新的檔案存放區

1. 以 RTCUniversersalServerAdmins 或 CsServerAdministrator 群組成員的身分登入電腦，商務用 Skype Server 安裝系統管理工具。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。

4. 針對使用您計畫要移除之檔案存放區的每個 director 集區、director、Standard Edition 伺服器及前端集區，選取伺服器或集區，按一下 [**動作**]，然後按一下 [**停止所有服務**]。

5. 以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

6. 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 拓撲** 產生器]。

7. 選取使用檔案存放區的伺服器或集區，然後執行下列作業：

8. 以滑鼠右鍵按一下伺服器或集區，然後按一下 [ **編輯屬性**]。

9. 在 [ **編輯屬性**] 的 [ **關聯**] 下，按一下 [檔案 **存放區**] 底下的 [ **新增**]

10. 在 [ **定義新的檔案存放區**] 的 [檔案 **伺服器 FQDN**] 下，輸入檔案伺服器的完整功能變數名稱 (FQDN) 。 在 [檔案 **共用**] 底下，輸入新檔共用的資料夾名稱，然後按一下 **[確定]**。

     > [!IMPORTANT]
     > 這個步驟會定義新的檔案存放區，以供拓撲產生器使用。 您只能將它定義一次，而不是針對每一部伺服器。 在發行拓撲之前，您必須在定義的檔案伺服器上建立已定義的檔案共用。 如需詳細資訊，請參閱[定義前端的檔案存放區](/previous-versions/office/communications/gg133895(v=ocs.14))。

11. 針對每個使用檔案存放區的伺服器或集區，執行下列作業：

12. 以滑鼠右鍵按一下伺服器或集區，然後按一下 [ **編輯屬性**]。

13. 在 [ **編輯屬性**] 的 [ **關聯**] 下，選取 [檔案 **存放區**] 中的新檔案共用，然後按一下 **[確定]**。

14. 發佈拓撲，檢查複寫狀態，然後視需要執行商務用 Skype Server 部署嚮導。 如需詳細資訊，請參閱＜[Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))＞。

15. 啟動命令提示字元：按一下 [ **開始**]，按一下 [ **執行**]，然後輸入 cmd.exe。

16. 在命令列輸入下列命令：

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S 參數會複製到檔案、目錄及子目錄。 /XF 參數會跳過名為 Meeting 的任何檔案。 使用/MT 參數的目前 robocopy.exe 版本，可使用多個執行緒大幅增加複製速度。 針對/LOG 參數使用目錄路徑和記錄檔案名，格式為 C:\Logfiles\log.txt。 此參數會在命名位置建立作業的記錄檔。

17. 當資料複本完成時，請按一下 [Lync Server 控制台] 中的 [ **拓撲**]，然後按一下 [ **狀態**]。

18. 針對您停止服務的每一部伺服器或集區，選取伺服器或集區，按一下 [ **動作**]，然後按一下 [ **啟動所有服務**]。

19. 從拓撲中移除舊的檔案存放區，然後發行拓撲。 如需詳細資訊，請參閱 [移除檔存放區](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))。

20.  (選用) 登入包含您剛才移除為本機 Administrators 群組成員或 Domain Admins 群組成員的電腦，然後移除舊的檔案共用及目錄。

## <a name="see-also"></a>另請參閱

[將伺服器重新指派至其他檔案存放區](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[移除檔存放區](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))