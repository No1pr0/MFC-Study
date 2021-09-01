# MFC-Study

CString Class
  - 특징 1 : ANSI, Unicode 문자열 지원
                                        
            [pjt properties]->[general]->Character Set = Use Unicode Character Set
            CString Ojt 생성 시 내부 문자열은 Unicode로 저장
            한글로 출력하기 위해서는 _tsetlocale(LC_ALL,_T("")); 코드 필요
  - 특징 2 : variable length 문자열 지원  
                                        
            프로그램 실행 중 문자열 길이 자유롭게 변환 가능 (최대 메모리 크기 : INT_MAX)
 
  - 특징 3 : const TCHAR* or LPCTSTR 대신 CString Ojt 직접 사용 가능
                                        
            두 타입을 인자로 받는 함수에 CString Ojt를 넘겨주면 알아서 문자열 값 전달
                                        
  - 예제 1 (CString::LoadString())
        
           CString str;
             str.LoadString(IDS_APP_TITLE); // 문자열 테이블에서 문자열 리소스를 불러옴.
             str.Insert(0,_T("Hello from ")); // 문자열 앞에 추가
             str.Append(_T("!")); // 문자열 뒤에 추가
             
  - 예제 2 (CString::Format())
 
          CString str;
             str.Format(_T("x = %d, y = %d\n"), 100, 200); //데이터를 문자열로 변환해서 버퍼에 출력
