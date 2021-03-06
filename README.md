# 목차
## 1. 앱 소개<br>
+ 주제 선정이유<br>
+ 주요 기능<br> 
+ 차별점<br>
+ 기타<br>
## 2. 기능구현
### 2-1 파이어베이스<br>
+ 소개<br>
+ 로그인<br>
+ 회원가입<br>
+ 메인화면<br>
### 2-2 리얼타임 데이터베이스<br>
+ 소개<br>
+ 데이터 저장<br>
### 2-3 구글맵<br>
+ 소개<br>
+ GoogleMap 구현<br>
+ 마커 찍기<br>
+ UserInfo_number 액티비티<br>
### 2-4 카메라 실행<br>
+ 카메라, 앨범 실행<br>
+ 이미지 불러오기<br>
### 2-5 이미지 저장 및 전송<br>
+ 이미지값 변환<br>
+ 이미지값 데이터 베이스에 저장<br>
### 2-6 전송된 이미지 확인<br>
### 2-7 환경설정<br>
+ 소개<br>
+ 환경설정 구성<br>
## 3. 동작영상
  
# 1. 앱 소개<br>
## 1-1 주제 선정이유<br>
<img width="600" alt="스모프 발표 사진" src="https://user-images.githubusercontent.com/79956770/121331013-76f16e80-c951-11eb-92f3-deebd9a82263.PNG"><br>
+  위에 그림과 같이 코로나19로 인해 우리나라를 찾는 방한 외래관광객과 해외로 여행가는 국민 해외여행객 숫자가 크게 감소한 것을 볼 수 있습니다.
   여행을 가고 싶지만, 여행을 가기 힘든 현실적인 상황을 고려해서, 원하는 여행지의 사진을 교환하는 기능을 통해, 여행에 대한 대리만족을 목적으로 주제를 선정하였습니다.
   <br>
   앱의 회원가입 및 파이어베이스를 이용한 데이터베이스 기능을 통해, 다양한 국적 및 많은 유저들이 이용할 수 있습니다.
   또한, 사진 전송 기능을 통해 사람들이 다양한 장소에 대한 사진들을 실시간으로 주고 받을 수 있습니다. <br>
   (참고 사이트 : https://m.blog.naver.com/gri_blog/221983041991)<br>
## 1-2 주요 기능<br>   
#### <파이어베이스>
<pre> 김규식 </pre>
#### <리얼타임 데이터베이스> 
<pre> 안준영, 장지민 </pre>
#### <구글맵>
<pre> 안준영 </pre>
#### <카메라 실행>
<pre> 이현호 </pre>
#### <이미지 저장 및 전송>
<pre> 안준영, 이현호, 장지민 </pre>
#### <환경설정>
<pre> 윤효묵 </pre>
## 1-3 차별점<br>
<pre> 작성자 - 안준영 - </pre><br>
<img src="https://user-images.githubusercontent.com/79949843/121353965-6220d500-c969-11eb-817f-facdce12f6f3.png"><img src="https://user-images.githubusercontent.com/79949843/121353987-6947e300-c969-11eb-9a0c-d1a2ea08f8fe.png"><br>
위와 같은 기존 sns는 수많은 사람들이 사진을 공유하고 소통, 공감하는데 있어 최고의 모습을 보여주고 있습니다.<br>
그러나, 기존 sns의 큰 문제점은 사진을 교환하거나 공유하는 기능이외의 너무 많은 기능들이 존재한다는 것과,<br>
실제 사진을 올리고, 자신의 일상이나 감정을 공유하는 사람은 실제 어플의 사용자의 절반도 되지 않는다는 것입니다.<br>
이러한 문제점을 해결하기 위해 우리조는 코로나로 인해 지친 일상속에서 누구나 다양한 일상 속 사진교환할 수 있는 어플을 만들고자 하였습니다.<br><br>
다른 앱과 우리 앱의 가장큰 차이점은 사진 교환을 위한 어플로 자유롭게 자신의 사진을 다른 유저에게 전송, 누가 전송하였는지 확인후 사진 교환<br>
받은 사진을 자신만의 앨범에서 개별로 확인할 수 있다는 것입니다.
## 1-4 기타<br>
### 아이디어
<pre> 안준영 </pre>
### 피피티 제작
<pre> 다같이 </pre>
### 피피티 병합/디자인
<pre> 안준영 </pre>
### 구현 영상 제작
<pre> 다같이 </pre>
### 구현 영상 병합
<pre> 장지민 </pre>
### 깃허브 외형 설계
<pre> 윤효묵 </pre>

# 2. 기능구현<br>
## 2-1 파이어베이스 - <br>
### (1) 소개
  
Firebase 에서 제공하는 서비스를 이용해 사용자를 식별할수 있는 ID / Passwrod 생성과 앱 활용에 필요한
각종 데이터들을 저장하기 위한 기능을 하는 파트 입니다<br>

사용자는 로그인 / 레지스터 / 메인 화면 3 가지 화면을 활용 합니다 <br>

### (2) 로그인
먼저 로그인 화면입니다 <br> 사용자는 로그인 화면에서 토스트 메시지를 참고해 규격에 맞지 않는 
ID / PW 작성을 인지할수 있습니다<br>
<pre><code> 
  mLoginBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String email = mEmail.getText().toString().trim(); // 사용자 이메일 인식
                String password = mPassword.getText().toString().trim();// 사용자 패스워드 인식

                if(TextUtils.isEmpty(email)){
                    mEmail.setError("Email is Required."); //이메일 작성칸에 이메일을 적지 않았을시 나오는 메시지
                    return;
                }

                if(TextUtils.isEmpty(password)){
                    mPassword.setError("Password is Required."); //패스워드 작성칸에 패스워드를 적지 않았을시 나오는 메시지
                    return;
                }

                if(password.length() < 8){
                    mPassword.setError("Password Must be >= 8 Characters"); //패스워드가 8자리 이상이 아닐시 나오는 메시지
                    return;
                }
    </code></pre> 
    
<br> 아래는 로그인 화면에서 가장 중요한 파이어 베이스에서 정보를 불러오는 코드입니다 <br>
fAuth.signInWithEmailAndPassword(email,password) 코드를 통해 이메일과 패스워드를 인증합니다 <br>

<pre><code> 
                fAuth.signInWithEmailAndPassword(email,password).addOnCompleteListener(new OnCompleteListener<AuthResult>() {
                    @Override
                    public void onComplete(@NonNull Task<AuthResult> task) {
                        if(task.isSuccessful()){
                            Toast.makeText(Login.this, "Logged in Successfully", Toast.LENGTH_SHORT).show();
                            startActivity(new Intent(getApplicationContext(),MapsActivity.class));
                        }else {
                            Toast.makeText(Login.this, "Error ! " + task.getException().getMessage(), Toast.LENGTH_SHORT).show();
                            progressBar.setVisibility(View.GONE);
                        }

                    }
                });
               </code></pre>

<br> 로그인 화면에서는 사용자가 비밀번호를 분실했을때 비밀번호를 다시 세팅 할 수 있는 서비스도 제공합니다 <br>
AlertDialog 기능을 사용해 사용자에 아아디, 즉 이메일 정보를 받아 해당 이메일에 패스워드 리셋 링크를 전송합니다 <br>
이때 전송에 실패 하거나 등록되지 않은 이메일을 작성했으면 Failure 메시지를 확인 할 수 있게 구현했습니다<br>
<pre><code>

       forgotTextLink.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                final EditText resetMail = new EditText(v.getContext());
                final AlertDialog.Builder passwordResetDialog = new AlertDialog.Builder(v.getContext());
                passwordResetDialog.setTitle("Reset Password ?");
                passwordResetDialog.setMessage("Enter Your Email To Received Reset Link.");
                passwordResetDialog.setView(resetMail);

                passwordResetDialog.setPositiveButton("Yes", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                            // extract the email and send reset link
                        String mail = resetMail.getText().toString();
                        fAuth.sendPasswordResetEmail(mail).addOnSuccessListener(new OnSuccessListener<Void>() {
                            @Override
                            public void onSuccess(Void aVoid) {
                                Toast.makeText(Login.this, "Reset Link Sent To Your Email.", Toast.LENGTH_SHORT).show();
                            }
                        }).addOnFailureListener(new OnFailureListener() {
                            @Override
                            public void onFailure(@NonNull Exception e) {
                                Toast.makeText(Login.this, "Error ! Reset Link is Not Sent" + e.getMessage(), Toast.LENGTH_SHORT).show();
                            }
                        });

                    }
                });

                passwordResetDialog.setNegativeButton("No", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        // close the dialog
                    }
                });
</code></pre>

마지막으로 로그인 페이지에서 회원가입(register) 로 넘어가기위한 버튼 입니다
<pre><code>
 mCreateBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(getApplicationContext(),Register.class));
            }
        });
</code></pre>

### (3) 회원가입

<br> 회원가입 페이지에서는 사용자에게 5가지 종류의 데이터를 작성받습니다. 이름, 이메일, 비밀번호, 전화번호, 국적 입니다 <br>
앱은 사용자의 정보를 받아 로그인 인증, 앱 내 서비스 이용에 해당 유저의 데이터를 활용합니다 <br>

<br>아래는 사용자의 데이터를 인식해 파이어베이스에 저장을 하기 위한 코드 입니다

<pre><code>
  Toast.maeText(Register.this, "User Created.", Toast.LENGTH_SHORT).show();
                            userID = fAuth.getCurrentUser().getUid();
                            DocumentReference documentReference = fStore.collection("users").document(userID);
                            Map<String,Object> user = new HashMap<>();
                            user.put("fName",fullName);
                            user.put("email",email);
                            user.put("phone",phone);
                            user.put("country",country);
                            documentReference.set(user).addOnSuccessListener(new OnSuccessListener<Void>() {
                                @Override
                                public void onSuccess(Void aVoid) {
                                    Log.d(TAG, "onSuccess: user Profile is created for "+ userID);
                                }
                            }).addOnFailureListener(new OnFailureListener() {
                                @Override
                                public void onFailure(@NonNull Exception e) {
                                    Log.d(TAG, "onFailure: " + e.toString());
                                }
                            });
  fDatabase = FirebaseDatabase.getInstance();

                            DatabaseReference reference = fDatabase.getReference();

                            Map<String, Object> childUpdates=new HashMap<>();

                            Map<String, Object> postValues=null;

                            com.androidapp.youjigom.FirebasePost post=new com.androidapp.youjigom.FirebasePost(image, fullName, country,senderName);
                            postValues=post.toMap();

                            setSenderName(fullName);

                            childUpdates.put("/users/"+fullName,postValues);
                            reference.updateChildren(childUpdates);

                            startActivity(new Intent(getApplicationContext(),MainActivity.class));

                        }else {
                            Toast.makeText(Register.this, "Error ! " + task.getException().getMessage(), Toast.LENGTH_SHORT).show();
                            progressBar.setVisibility(View.GONE);
                        }
                    }
                });
            }
        });


</pre></code>

<br> 로그인 화면에서와 마찬가지로 사용자가 잘못된 정보를 기입할 수도 있기 때문에 잘못된 정보 작성에 대한 정보 또한 제공합니다 <br>
<pre><code>
 mRegisterBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                final String email = mEmail.getText().toString().trim();
                String password = mPassword.getText().toString().trim();
                final String fullName = mFullName.getText().toString();
                final String phone    = mPhone.getText().toString();
                final String country = mCountry.getText().toString().toString();

                if(TextUtils.isEmpty(email)){
                    mEmail.setError("Email is Required.");
                    return;
                }
                if(TextUtils.isEmpty(password)){
                    mPassword.setError("Password is Required.");
                    return;
                }
                if(password.length() < 6){
                    mPassword.setError("Password Must be >= 6 Characters");
                    return;
                }
                if(TextUtils.isEmpty(country)){
                    mCountry.setError("Country information is required");
                    return;
                }
                progressBar.setVisibility(View.VISIBLE);
</pre></code>

<br> 사용자가 정보를 작성 할 때, 국적(country) 값은 정해진 답변에서만 선택 해야 합니다 <br>
주어진 옵션에서만 선택 할 수 있도록 AlertDialog 시스템을 구현헀습니다<br>

<pre><code>
 final int[] selectedItem = {0};

        choose = (Button) findViewById(R.id.choose);
        choose.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View v) {
                final String[] items = new String[]{
                        "미국",//0
                        "영국",//1
                        "프랑스",//2
                        "남아프리카공화국",//3
                        "이탈리아",//4
                        "사우디아라비아",//5
                        "인도",//6
                        "러시아",//7
                        "멕시코",//8
                        "브라질",//9
                        "아르헨티나",//10
                        "태국",//11
                        "중국",//12
                        "일본",//13
                        "대한민국"};//14
                AlertDialog.Builder dialog = new AlertDialog.Builder(Register.this);
                dialog.setTitle("Choose your country")
                        .setSingleChoiceItems(items, 0, new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int which) {
                                selectedItem[0] = which;
                                mCountry.setText(items[selectedItem[0]]);

                            }
                        })
                        .setPositiveButton("confirm", new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int which) {

                                Toast.makeText(Register.this
                                        ,items[selectedItem[0]]
                                        ,Toast.LENGTH_SHORT).show();
                            }
                        })
                        .setNeutralButton("back", new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int which) {
                                Toast.makeText(Register.this
                                        ,"Canceled"
                                        ,Toast.LENGTH_SHORT).show();
                            }
                        });
                dialog.create();
                dialog.show();

            }
        });
</pre></code>

<br> 마지막으로 로그인 화면에 다시 돌아갈 수 있도록 해주는 버튼 입니다 <br>
<pre><code>
        mLoginBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(new Intent(getApplicationContext(),Login.class));
            }
        });

</pre></code>

### (4) 메인화면<br>

<br> 메인화면은 사용자가 최종적으로 개인정보 등을 다 입력해 앱 사용을 시작하는 화면입니다
<br> 메인 화면에서는 사용자가 기입한 정보 프로필, 아이디 등등 변경이 가능합니다 <br>
위를 구현하기 위해서는 우선 파이어베이스에서 정보를 불러 올 수 있는 코드들이 필요합니다 <br>
이번 프로젝트에서 활용하지는 않았지만 서버에 저장된 이미지를 불러오는 기능인 picasso 또한 코드로 작성했습니다
<pre><code>
 fAuth = FirebaseAuth.getInstance();
        fStore = FirebaseFirestore.getInstance();
        storageReference = FirebaseStorage.getInstance().getReference();

        StorageReference profileRef = storageReference.child("users/"+fAuth.getCurrentUser().getUid()+"/profile.jpg");
        profileRef.getDownloadUrl().addOnSuccessListener(new OnSuccessListener<Uri>() {
            @Override
            public void onSuccess(Uri uri) {
                Picasso.get().load(uri).into(profileImage);
            }
        });
</pre></code>

<br> 메인 화면에서 가장 중요한 기능중 하나는 이메일 인증입니다. <br>
사용자는 로그인에 사용되는 이메일을 통해 본인이 맞는지 인증 하는 메일을 받고 링크를 실행하여야 합니다 <br>
<pre><code>
if (!user.isEmailVerified()) {
            verifyMsg.setVisibility(View.VISIBLE);
            resendCode.setVisibility(View.VISIBLE);

            resendCode.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(final View v) {
                    user.sendEmailVerification().addOnSuccessListener(new OnSuccessListener<Void>() {
                        @Override
                        public void onSuccess(Void aVoid) {
                            Toast.makeText(v.getContext(), "Verification Email Has been Sent.", Toast.LENGTH_SHORT).show();
                        }
                    }).addOnFailureListener(new OnFailureListener() {
                        @Override
                        public void onFailure(@NonNull Exception e) {
                            Log.d("tag", "onFailure: Email not sent " + e.getMessage());
                        }
                    });
                }
            });
        }
</pre></code>

<br> 회원가입에서 기입한 사용자 정보들을 불러오기위한 코드들 입니다 <br>
<pre><code>
 DocumentReference documentReference = fStore.collection("users").document(userId);
        documentReference.addSnapshotListener(this, new EventListener<DocumentSnapshot>() {
            @Override
            public void onEvent(@Nullable DocumentSnapshot documentSnapshot, @Nullable FirebaseFirestoreException e) {
                if (documentSnapshot != null && documentSnapshot.exists()) {
                    phone.setText(documentSnapshot.getString("phone"));
                    fullName.setText(documentSnapshot.getString("fName"));
                  email.setText(documentSnapshot.getString("email"));
                  country.setText(documentSnapshot.getString("country"));

                } else {
                    Log.d("tag", "onEvent: Document do not exists");
                }
            }
        });
</pre></code>

<br>  패스워드 변경기능입니다 <br>
<br> 패스워드를 이메일 인증을 통해 완전히 바꾸는것과는 다른 패스워드를 변경하는 기능입니다 <br>
<br> 사용자가 패스워드 규격에 맞지 않는 정보를 입력하면 에러 메시지를 보여줍니다 <br>
<pre><code>
 resetPassLocal.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                final EditText resetPassword = new EditText(v.getContext());

                final AlertDialog.Builder passwordResetDialog = new AlertDialog.Builder(v.getContext());
                passwordResetDialog.setTitle("Reset Password ?");
                passwordResetDialog.setMessage("Enter New Password > 8 Characters long.");
                passwordResetDialog.setView(resetPassword);

                passwordResetDialog.setPositiveButton("Yes", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        // extract the email and send reset link
                        String newPassword = resetPassword.getText().toString();
                        user.updatePassword(newPassword).addOnSuccessListener(new OnSuccessListener<Void>() {
                            @Override
                            public void onSuccess(Void aVoid) {
                                Toast.makeText(MainActivity.this, "Password Reset Successfully.", Toast.LENGTH_SHORT).show();
                            }
                        }).addOnFailureListener(new OnFailureListener() {
                            @Override
                            public void onFailure(@NonNull Exception e) {
                                Toast.makeText(MainActivity.this, "Password Reset Failed.", Toast.LENGTH_SHORT).show();
                            }
                        });
                    }
                });

                passwordResetDialog.setNegativeButton("No", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        // close
                    }
                });

                passwordResetDialog.create().show();

            }
        });
       </pre></code>

<br> 마지막으로 메인 액티비티는 다른 화면으로 넘어 갈 수 있도록 하는 각종 버튼들이 존재합니다
<br> 그러한 버튼들을 이용할 수 있게 해주는 코드들입니다

앨범
<pre><code>
 ImgList = findViewById(R.id.btnImgList);
        ImgList.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                startActivity(new Intent(getApplicationContext(),imgList.class));
            }
        });
 </pre></code>
 로그아웃
 <pre><code>
public void logout(View view) {
        FirebaseAuth.getInstance().signOut();//logout
        startActivity(new Intent(getApplicationContext(), Login.class));
        finish();
    }
</pre></code>
옵션메뉴
<pre><code>
    public boolean onCreateOptionsMenu(Menu menu) {
        MenuInflater inflater = getMenuInflater();
        inflater.inflate(R.menu.menu, menu);
        return true;
    }
</pre></code>

    
    


## 2-2 리얼타임 데이터베이스 - 
### (1) 소개<br>
<img src="https://user-images.githubusercontent.com/79952145/121284977-961fda00-c918-11eb-9c80-2c9bc1e5b664.png" align="left" height="300">
Realtime Database는 Firebase에서 제공하는 실시간 데이터베이스로 데이터 저장 및 동기화가 실시간으로 가능한 데이터베이스입니다. <br><br>
왼쪽 사진과 같이 Firebase 콘솔을 통해 접속할 수 있고, 이 앱에서는 회원가입한 사용자의 일부 정보를 저장하고 전송된 이미지를 스트링 값으로 변환하여 저장하는 곳에 사용했습니다.<br><br><br><br><br><br><br><br><br>

### (2) 데이터 저장<br>
<b>회원가입한 사용자의 정보 중 이름과 국가 정보 저장<br></b><br>
각 데이터를 저장하기 위해서 FirebasePost 자바 파일을 만들어 그 안에 필요한 변수들과 함수를 작성해줍니다.<br>

  <pre><code>
    public String image;
    public String fullName;
    public String country;
    public String senderName;

    public FirebasePost() {
    }

    public FirebasePost(String image, String fullName, String country, String senderName) {
        this.image = image;
        this.fullName = fullName;
        this.country = country;
        this.senderName = senderName;
    }
       </code></pre>
       
toMap 함수는 Realtime Database에 값을 저장하기 위해 HashMap 형식으로 데이터를 넣어줄 함수입니다.<br> 
처음 회원가입시에는 이미지 전송을 하지 않은 상태이기 때문에 fullName과 country정보만 데이터베이스에 저장되게 됩니다.<br>

<pre><code>
    public Map<String, Object> toMap() {
        HashMap<String, Object> result = new HashMap<>();
        result.put("image",image);
        result.put("fullName",fullName);
        result.put("country",country);
        result.put("senderName",senderName);

        return result;
    }
   </code></pre>
   
회원가입을 하면 정보들이 데이터베이스에 저장되도록 회원가입 버튼에 onClick리스너 안에 데이터 저장 코드를 작성해줍니다.<br>
<pre><code>
   fDatabase = FirebaseDatabase.getInstance();
   DatabaseReference reference = fDatabase.getReference();

   Map<String, Object> childUpdates=new HashMap<>();
   Map<String, Object> postValues=null;
   </code></pre>

필요한 변수를 선언해주고 FirebasePost 클래스에 작성해놓은 toMap함수를 이용하여 데이터베이스에 데이터를 저장해줍니다.<br>

<pre><code>
   com.androidapp.youjigom.FirebasePost post=new com.androidapp.youjigom.FirebasePost(image, fullName, country,senderName);
   postValues=post.toMap();

   childUpdates.put("/users/"+fullName,postValues);
   reference.updateChildren(childUpdates);
   </code></pre>
   
앱을 실행하여 회원가입을 해보면 image와 senderName값은 널값이므로 들어가지 않고 나머지 부분을 잘 저장된 것을 확인할 수 있습니다.<br>
<img src="https://user-images.githubusercontent.com/79952145/121284733-48a36d00-c918-11eb-98b1-0755e825b56a.png"><br>

## 2-3 구글맵 - 안준영<br><br>
+ 소개<br><br>
<img width="300" src="https://user-images.githubusercontent.com/79949843/121337394-75c34000-c957-11eb-80d8-c24e6a759611.png"><img src="https://user-images.githubusercontent.com/79949843/121337659-bb800880-c957-11eb-9372-46229a914003.png"><br>
저희 조는 구글맵을 이용하여 다양한 사용자들과의 접근을 쉽게하고, <br>
리얼타임 데이터베이스를 이용하여 교환하는 이미지의 정보를 쉽게 전송, 저장 할 수있게 하였습니다.<br><br>
아래 내용으로는 제가 구현한 기능들을 어떻게 구현했고, 처음보는 사람도 쉽게 따라할 수 있게 내용들을 기록하였습니다.<br><br>
+ GoogleMap 구현<br><br>
구글맵API를 실현하기 위한 프로젝트를 만들어줍니다.<br>
프로젝트를 만들었으면 아래 사진과 같이 Google Map Activity를 생성해줍니다.<br>File->New->Google->Google Maps Activity<br>
<img src = "https://user-images.githubusercontent.com/79949843/114507804-9bd9a600-9c6e-11eb-8e79-e3d8dafa6e6e.PNG" width="600px"><br><br>
res -> value -> google_maps_api.xml url로 들어가 프로젝트 생성 후 API키값을 받아옵니다.<br>
<img src = "https://user-images.githubusercontent.com/79949843/114509929-0b509500-9c71-11eb-904c-7420f44bb256.PNG"><br><br>
키값을 받았으면 다시 안드로이드 스튜디오로 가서 res -> value -> google_maps_api.xml에 있는 "YOUR_KEY_HERE" 부분에 키값을 넣어줍니다.<br>
<pre><code>

    //생략...
    
    https://console.developers.google.com/flows/enableapi?apiid=maps_android_backend&keyType=CLIENT_SIDE_ANDROID&r=FA:32:8D:A5:DB:85:6A:1D:0F:62:5B:F2:75:B7:8A:29:55:9A:F5:7A%3Bcom.androidapp.tobeacontinue
   
   //생략...
   
    < string name="google_maps_key" templateMergeStrategy="preserve" translatable="false">YOUR_KEY_HERE< /string>
© 2020 GitHub, Inc.


</code></pre>
<br>
키 값을 넣은 다음 Gradle Script->build.gradle(Module:프로젝트이름.app)에서 다음과 같은 코드를 추가해줍니다.<br>
<pre><code>
        dependencies {
                implementation fileTree(dir: 'libs', include: ['*.jar'])
                implementation 'androidx.appcompat:appcompat:1.2.0'
                                     .
                                     .
                implementation 'com.google.android.gms:play-services-maps:17.0.0'
                implementation 'com.google.android.gms:play-services-location:18.0.0'
                                     .
                                     .
                                     .
                }       
</code></pre><br>
다음으로는 AndroidManifast.xml에서 해당 코드를 추가해 준다. "API 키" 부분에는 아까 받아온 키값을 넣어줍니다.<br>
<pre><code>

  < meta-data
            android:name="com.google.android.geo.API_KEY"
            android:value="API 키"/>
  

</code></pre><br>
위와 같은 내용을 실행한 뒤 MapsActivity onMapReady메소드 내부에 구글맵을 어떻게 구상할지 코드해 주었습니다.<br><br>
+ 마커 찍기<br><br>
  (1) 다중 마커<br><br>
  다중마커 구현입니다.<br>
  다양한 나라의 사람들과 사진 교환을 목적으로 하기 때문에 다중 마커를 구현하였습니다.
  저는 마커를 추가할 나라의 좌표값들을 Locations라는 자바파일에 이중 배열로 저장한 뒤 위도와 경도값을 한번에 가져와서 설정해 주었습니다.<br>
  먼저 Locatinos 자바파일 내부 코드 입니다.<br>
  <pre><code>
  public class Locations {

    final static double[][] LatLng = {
        //위도와 경도값 이중 배열로 저장
            {39.09843569786831, -77.03655778803672},//0
            {51.5144591527327, -0.12975831845500382},//1
            //생략..
            {35.74306540022329, 139.77245318272045},//13
            {37.557667, 126.926546}//14

    };
    
    final static String[] countryName = {
        //위 배열의 순서대로 국가의 이름 스트링값으로 저장
            "미국",//0
            "영국",//1
            //생략..
            "일본",//13
            "대한민국"//14
                 };
        }
  </code></pre>
  MapsActivity에서 다음과 같은 코드로 다중 마커를 구현하였습니다<br>
  <pre><code>
  //Locations 클래스에서 좌표값을 가져오기 위하여 선언
  static Locations locations = new Locations();
    double[][] locationsdata = locations.LatLng;
    //생략..
    @Override
    public void onMapReady(GoogleMap googleMap) {
    
        //for문을 이용한 다중마커 구현
        for (int x = 0; x < 15; x++) {
            // 이중 배열을 이용한 위도값 설정 
            double lat = locationsdata[x][0];
            // 이중 배열을 이용한 경도값 설정 
            double lon = locationsdata[x][1];
            LatLng latLng = new LatLng(lat, lon);
            //LatLng latLng = new LatLng(37.557667, 126.926546);

            // 카메라를 설정 위치로 옮긴다
            googleMap.moveCamera(CameraUpdateFactory.newLatLng(latLng));
            //구글 맵에 표시할 마커에 대한 옵션 설정
            MarkerOptions markerOptions = new MarkerOptions().position(latLng).title(CountryName[x]);
            // 마커 생성
            googleMap.addMarker(markerOptions);
        }
        // 카메라 줌 정도를 설정한다
        googleMap.moveCamera(CameraUpdateFactory.zoomTo(0));
        //마커 클릭 이벤트 추가
        googleMap.setOnMarkerClickListener(this::OnMarkerClick);
    }
  </code></pre><br><br>
  (2) 마커 클릭<br><br>
  아래 코드로 마커 클릭 이벤트를 추가해 줍니다.<br>
  <pre><code>
    //마커 클릭 이벤트 추가
        googleMap.setOnMarkerClickListener(this::OnMarkerClick);
  </code></pre><br>
  해당 앱에서는 나라별 마커 클릭시 다른 액티비티로 이어다. 다음 코드를 보면 알수 있습니다.
  <pre><code>
  //마커를 클릭할 시 발생할 내용을 해당 메소드 내부에 코딩
  public boolean OnMarkerClick(Marker marker) {
       
        LatLng countryLocation = marker.getPosition();

        //미국 마커 클릭시
        //새로운 변수를 만들어줘 미국 좌표값을 대입
        double lat0 = locationsdata[0][0];
        double lon0 = locationsdata[0][1];
        LatLng latLng0 = new LatLng(lat0, lon0);
        //미국의 좌표값을 가져와 사용자가 클릭한 마커와 미국의 마커와 동일한 경우 미국의 UserInfo 액티비티가 열린다
        if (countryLocation.equals(latLng0)) {
            startActivity(new Intent(getApplicationContext(), UserInfo_0.class));
        }
        //동일한 방법으로 Locations 파일 내부 배열의 크기만큼 코드
        //영국 마커 클릭시
        double lat1 = locationsdata[1][0];
        double lon1 = locationsdata[1][1];
        LatLng latLng1 = new LatLng(lat1, lon1);

        if (countryLocation.equals(latLng1)) {
            startActivity(new Intent(getApplicationContext(), UserInfo_1.class));
        }
        //생략..
        //일본 마커 클릭시
        double lat13 = locationsdata[13][0];
        double lon13 = locationsdata[13][1];
        LatLng latLng13 = new LatLng(lat13, lon13);

        if (countryLocation.equals(latLng13)) {
            startActivity(new Intent(getApplicationContext(), UserInfo_13.class));
        }

        //대한민국 마커 클릭시
        double lat14 = locationsdata[14][0];
        double lon14 = locationsdata[14][1];
        LatLng latLng14 = new LatLng(lat14, lon14);

        if (countryLocation.equals(latLng14)) {
            startActivity(new Intent(getApplicationContext(), UserInfo_14.class));
        }

        return false;
    }
  </code></pre><br><br>
+ UserInfo_number 액티비티<br><br>
이번에는 UserInfo 액티비티 내부 코드와 기능에대해 알아보겠습니다.<br>
UserInfo 액티비티는 리얼타임 데이터베이스에서 사용자들의 정보를 불러와 나라별로 리스트뷰를 만들기 위한 목적으로 생성해 주었습니다.<br>
<img height = "300" width = "300" src = "https://user-images.githubusercontent.com/79949843/121343520-bfaf2480-c95d-11eb-8349-493de07fb33e.png"><br>
Locations 자바파일에서 나라의 좌표값을 15개 지정해 주었기 때문에 15개의 액티비티를 생성해 주었고 많은 수의 파일을 관리하기 용이하기 위해<br>
UserInfo_Number 라는 Package를 새로 만들어 해당 패키지 내부에 모든 액티비티를 저장하였습니다.<br>
<img src = "https://user-images.githubusercontent.com/79949843/121344373-a9559880-c95e-11eb-949f-f35eebc23e05.png"><br>
<img height = "500" width = "300" src = "https://user-images.githubusercontent.com/79949843/121344312-9642c880-c95e-11eb-8eb3-e00aefbd0cdc.png"><br>
또한 layout파일의 수를 줄이기 위해 다음과 같이 ListView를 기반으로 하는 layout을 하나 만들어 준 뒤 모든 UserInfo 액티비티들이 해당 layout을 참조하게 하였습니다.<br><br>
  (1) 리스트 뷰<br><br>
  리스트뷰를 구성하는 코드들을 알아보겠습니다. 제일 먼저 ListView와 이를 연결해줄 ArrayAdepter를 선언해 줍니다.
  <pre><code>
  ListView dBListView;
  ArrayAdapter<String> adapter;
  </code></pre><br>
  다음으로는 onCreate메소드 내부에도 다음과같이 변수를 선언해 주고, ListView와 ArrayAdepter 연결해 줍니다.
  <pre><code>
        dBListView=findViewById(R.id.DBListView);

        adapter = new ArrayAdapter<String>(this,
                android.R.layout.simple_list_item_1);
                //simple_list_item_1은 안드로이드 스튜디오에서 제공해주는 가장 기본적은 ListView의 layout이다
        dBListView.setAdapter(adapter);
        getFirebaseDataBase();
        //getFirebaseDataBase은 ListView의 내부 아이템들의 내용을 채워주는 메소드, 아래 설명 참고
  </code></pre><br><br>
  (2) item클릭<br><br>
  리스트뷰를 구성했으니 내부에 있는 item에 클릭 메소드를 달아주겠습니다. 다음과 같은 코드를 추가해 주면 됩니다.
  <pre><code>
  dBListView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {

                receiverName = userName.get(position);
                receiverCountry = userCountry.get(position);
                //몇번째 item을 클릭하였는지 position을 통해 알고, 클릭한 정보를 저장해준다
                // 아래 나올내용과 관련이 많으니 기억해두자
                showMessage();
                //item 클릭시 발생하는 AlertDialog 구현 메소드, 아래 설명 참고

            }
        });
  </code></pre><br><br>
+ 리얼 타임 데이터베이스<br><br>
UserInfo 액티비티의 리스트뷰 내부 아이템들은 해당 국가에 포함된 유저들의 정보로 구성할 것이기 때문에 <br>
리얼타임 데이터베이스에서 country값이 일치하는 유저들을 전부 불러와야 합니다.<br><br>
  (1) 데이터 불러오기<br><br>
  리얼타임 데이터베이스에서 정보를 불러오는 코드는 addValueEventListener가 있습니다.<br>
  아까 위에서 말했던 getFirebaseDataBase() 메소드 내부의 코드를 보겠습니다.
  <pre><code>
  private void getFirebaseDataBase() {
        //리얼타임 데이터베이스에서 정보를 불러오는 addValueEventListener
        ValueEventListener eventListener = new ValueEventListener() {
            @Override
            //onDataChange 메소드는 리얼타임 데이터 베이스가 바뀔 때 마다 반응하는 비동기식 메소드 입니다.
            public void onDataChange(@NonNull DataSnapshot snapshot) {
                userName.clear();
                userCountry.clear();
                arrayData.clear();
                arrayIndex.clear();
                for(DataSnapshot dataSnapshot : snapshot.getChildren()){
                    String key=dataSnapshot.getKey();
                    com.androidapp.youjigom.FirebasePost get=dataSnapshot.getValue(com.androidapp.youjigom.FirebasePost.class);
                    String info[]={get.fullName, get.country};
                    
                    //해당 UserInfo 액티비티와 같은 country값을 가지는 유저들의만 정보를 불러옵니다.
                    if(info[1].equals(CountryName[0])){
                        String result = "사용자 이름 : " + info[0] + "\n국적 : " + info[1];
                        //String result=info[2];
                        arrayData.add(result);
                        arrayIndex.add(key);
                        userName.add(info[0]);
                        userCountry.add(info[1]);
                    }
                }
                adapter.clear();
                adapter.addAll(arrayData);
                adapter.notifyDataSetChanged();
            }

            @Override
            public void onCancelled(@NonNull DatabaseError error) {

            }
        };
    }
  </code></pre><br>
  위 코드를 통해 데이터를 불러오고 해당 데이터를 배열에 저장 -> 어뎁터를 통해 리스트뷰에 출력 하는것을 볼 수 있습니다.<br>
  그러나, 위 주석에서 언급한것처럼 onDataChange 메소드는 비동기식 메소드 이기 때문에 데이터가 바뀔때마다<br>
  리얼타임 데이터베이스의 모든 정보가 배열 내부에 중첩이 될 수 있습니다. 그러므로 메소드가 실행되기 전에 배열들을 초기화 해주는 모습을 볼 수 있습니다.<br><br>
  (2) 이미지 전송/ AlertDialog<br><br>
  저희 앱의 주 기능인 사진전송은 item을 클릭 하였을 때 구현하였습니다.<br>
  그러나, 앱을 사용하는 유저들이 잘못 눌렀을 경우를 방지하기위하여 item 클릭 이벤트에 <br>
  dialog를 추가해 주어 사진을 정말 전송할 것인지 재차 물어는 기능을 구현하였습니다. 아래 코드는 item 클릭 시 AlertDialog 구현 코드 입니다.
  <pre><code>
  public void showMessage(){
        // 다이올로그를 빌드해줄 변수를 선언합니다.
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("사진 교환");
        builder.setMessage( receiverName + "님께 사진을 전송하시겠습니까?" );
        //아이콘에 원하는 이미지 첨부
        builder.setIcon(R.drawable.adialog);
        //예를 클릭하였을 때
        builder.setPositiveButton("예", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                //FirePost 내부 리얼타임 데이터 베이스에 값을 저장해주는 메소드를 선언
                Map<String, Object> childUpdates=new HashMap<>();
                Map<String, Object> postValues=null;
                //카메라 액티비티에서 이미지의 주소 선언
                CameraActivity ca = new CameraActivity();
                String StringImage=ca.getoriginalBm();

                Register rg = new Register();
                // 보내는 사용자의 이름
                senderName = rg.getSenderName();

                com.androidapp.youjigom.FirebasePost post=
                        new com.androidapp.youjigom.FirebasePost
                                (StringImage, receiverName, receiverCountry, senderName);
                postValues=post.toMap();
                // 위에서 클릭한 사용자의 리얼타임데이터베이스 child에 StringImage와 senderName 저장
                childUpdates.put("users/" + receiverName, postValues);
                databaseReference.updateChildren(childUpdates);
            }
        });
        //아니요를 클릭하였을 때
        builder.setNegativeButton("아니요", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {

            }
        });
        AlertDialog alertDialog = builder.create();
        alertDialog.show();
    }
  </code></pre><br><br>
  ### 구현 영상
  아래 링크는 팀원들과 동영상을 병합하는 과정에서 제 구현 영상의 핸드폰으로 녹화한 영상이라 길이에 비해 용량이 너무커 별도로 올린 구현영상입니다.<br>
  시청해주시면 감사하겠습니다.<br>
  https://www.youtube.com/watch?v=FqLL_IXIqI8&feature=youtu.be
  


## 2-4 카메라 실행 - <br>
### (1) 카메라, 앨범 실행<br><br>

TedPermision()을 이용하여 CameraActivity 실행시 카메라 사용과 저장소 접근에 대한 서용 권한 체크 창을 띄우고 Gallery 버튼과 Camera 버튼 클릭 시 권한이 허락 되어 있다면 각 버튼의 이름에 맞는 함수를 호출하도록 했습니다.
<pre><code>
    @Override
  protected void onCreate(@Nullable Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
      setContentView(R.layout.activity_get_image);

      upload = findViewById(R.id.upload);
      btnCamera= findViewById(R.id.btnCamera);
      btnGallery = findViewById(R.id.btnGallery);
      upload.setVisibility(View.INVISIBLE);

      tedPermission();

      findViewById(R.id.btnGallery).setOnClickListener(new View.OnClickListener() {
          @Override
          public void onClick(View view) {
              if(isPermission) goToAlbum();
              else Toast.makeText(view.getContext(), getResources().
                      getString(R.string.permission_2), Toast.LENGTH_LONG).show();
          }
      });
      findViewById(R.id.btnCamera).setOnClickListener(new View.OnClickListener() {
          @Override
          public void onClick(View view) {
              if(isPermission)  takePhoto();
              else Toast.makeText(view.getContext(), getResources().
                      getString(R.string.permission_2), Toast.LENGTH_LONG).show();
          }
      });
  }
</code></pre>
앨범 버튼 클릭 시 goToAlbum()이라는 함수를 수행하게 되며 함수에서는 이미지의 선택 방법을 확인 할 수 있는 isCamera를 false로 선언해 주고 안드로이드 내에서 제공 하는 앨범의 사진 선택 화면으로 Intent를 전환해 줍니다. 이미지를 선택한 후 선택 분기를 결정하는 인텐트로 전환해 줍니다.
  <pre><code>
  private void goToAlbum() {
        isCamera = false;
        Intent intent = new Intent(Intent.ACTION_PICK);
        intent.setType(MediaStore.Images.Media.CONTENT_TYPE);
        startActivityForResult(intent, PICK_FROM_ALBUM);
    }
  </pre></code>
카메라 버튼 클릭 시 takephoto() 라는 함수를 수행하게 되며 isCamera를 true로 선언하여 Camera로 이미지를 선택했음을 알려주고 안드로이드 에서 제공하는 사진 촬영 인텐트로 전환합니다. 그 다음 createImageFile() 함수를 수행하여 이미지가 담길 임시 파일인 tempfile 만든 다음 FileProvider를 이용하여 tempfile의 uri값을 얻어오고 선택 분기를 결정하는 인텐트로 전환해 줍니다. 
   <pre><code>
   private void takePhoto() {
        isCamera = true;
        Intent intent = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
        try {
            tempFile = createImageFile();
        } catch (IOException e) {
            Toast.makeText(this, "이미지 처리 오류! 다시 시도해주세요.", Toast.LENGTH_SHORT).show();
            finish();
            e.printStackTrace();
        }
        if (tempFile != null) {
            if (android.os.Build.VERSION.SDK_INT >= android.os.Build.VERSION_CODES.N) {
                Uri photoUri = FileProvider.getUriForFile(this,
                        "com.androidapp.youjigom", tempFile);
                intent.putExtra(MediaStore.EXTRA_OUTPUT, photoUri);
                startActivityForResult(intent, PICK_FROM_CAMERA);
            } else {
                Uri photoUri = Uri.fromFile(tempFile);
                intent.putExtra(MediaStore.EXTRA_OUTPUT, photoUri);
                startActivityForResult(intent, PICK_FROM_CAMERA);
            }
        }
    }
   </pre></code>
onActivityResult를 이용하여 선택 분기에 따른 이벤트를 처리해 줍니다. 카메라 혹은 앨범에서 사진 선택 과정중 활동을 취소했을 경우 Toast메시지를 송출하고 tempfile을 삭제 시켜 줍니다.<br><br>
앨범에서 사진을 선택했을 경우는 우선 이미지의 URI를 얻어온 뒤 Cursor를 이용하여 URI 스키마를 Content:// 에서 File://로 변경한 뒤  이미지를 띄우는 Setimage()함수를 선언합니다.<br><br>
카메라에서 찍은 사진을 선택했을 경우에는 SetImage()함수를 선언합니다.
   <pre><code>
   if (requestCode == PICK_FROM_ALBUM) {
            Uri photoUri = data.getData();
            Log.d(TAG, "PICK_FROM_ALBUM photoUri : " + photoUri);

            Cursor cursor = null;
            try {
                String[] proj = {MediaStore.Images.Media.DATA};
                assert photoUri != null;
                cursor = getContentResolver().query(photoUri, proj, null, null, null);
                assert cursor != null;
                int column_index = cursor.getColumnIndexOrThrow(MediaStore.Images.Media.DATA);
                cursor.moveToFirst();
                tempFile = new File(cursor.getString(column_index));
                Log.d(TAG, "tempFile Uri : " + Uri.fromFile(tempFile));
            } finally {
                if (cursor != null) {
                    cursor.close();
                }
            }
            setImage();
        } else if (requestCode == PICK_FROM_CAMERA) {
            setImage();
        }
    }
  </pre></code>
createImageFile을 통해서 선택한 이미지가 담길 임시 파일을 생성합니다 파일의 이름은 중복을 피하기 위해서 해당 활동을 시작한 시간으로 지정합니다.
  <pre><code>
  private File createImageFile() throws IOException {
        String timeStamp = new SimpleDateFormat("HHmmss").format(new Date());
        String imageFileName = "KNLBDC_" + timeStamp + "_";
        File storageDir = new File(Environment.getExternalStorageDirectory() + "/KNLBDC/");
        if (!storageDir.exists()) storageDir.mkdirs();
        File image = File.createTempFile(imageFileName, ".jpg", storageDir);
        Log.d(TAG, "createImageFile : " + image.getAbsolutePath());
        return image;
    }
  </pre></code>
### (2) 이미지 불러오기<br>

tempfile을 사진을 조정하는 ImageResizeUtils 클래스의 resizeFile 함수를 이용하여 크기를 조정하고 비트맵 형식으로 변환하여 ImageView에 표시해 줍니다. 업로드 버튼 클릭시 이미지를 전송하는 Activity로 인텐트를 전환합니다.
<pre><code>
private void setImage() {
        imageView = findViewById(R.id.imageView);
        ImageResizeUtils.resizeFile(tempFile, tempFile, 1280, isCamera);

        BitmapFactory.Options options = new BitmapFactory.Options();
        Bitmap originalBm = BitmapFactory.decodeFile(tempFile.getAbsolutePath(), options);
        Log.d(TAG, "setImage : " + tempFile.getAbsolutePath());

        imageView.setImageBitmap(originalBm);
        StringImage=BitmapToString(originalBm);
        setoriginalBm(StringImage);

        upload.setVisibility(View.VISIBLE);
        btnCamera.setVisibility(View.INVISIBLE);
        btnGallery.setVisibility(View.INVISIBLE);

        findViewById(R.id.upload).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                //업로드 버튼 클릭 시 MapsActivity로 화면 전환
                startActivity(new Intent(getApplicationContext(),MapsActivity.class));
            }
        });
    }
</pre></code>

## 2-5 이미지 저장 및 전송<br>
### (1) 이미지값 변환<br><br>
BitmaptoString이라는 함수를 이용해서 비트맵 형식의 파일을 String값으로 전환합니다. 먼저 비트맵 파일을 Byte형식의 행렬에 저장한  그것을 String 값으로 전환해 줍니다.
<pre><code>
public static String BitmapToString(Bitmap bitmap) {
        ByteArrayOutputStream baos = new ByteArrayOutputStream();
        bitmap.compress(Bitmap.CompressFormat.PNG, 70, baos);
        byte[] bytes = baos.toByteArray();
        String temp = Base64.encodeToString(bytes, Base64.DEFAULT);
        return temp;
    }
</pre></code>

### (2) 이미지값 데이터 베이스에 저장<br><br>

<pre><code>
public void showMessage(){

        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("사진 교환");
        builder.setMessage( receiverName + "님께 사진을 전송하시겠습니까?" );
        builder.setIcon(R.drawable.adialog);
</pre></code>

리스트뷰에서 사진을 전송할 대상을 선택하고 위의 코드로 작성된 알림창이 뜨게 됩니다.<br><br>

<img src="https://user-images.githubusercontent.com/79952145/121300607-07b85200-c932-11eb-8ce0-9c18a2e8dd9c.png"><br>

<pre><code>
builder.setPositiveButton("예", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                Map<String, Object> childUpdates=new HashMap<>();
                Map<String, Object> postValues=null;
                CameraActivity ca = new CameraActivity();
                String StringImage=ca.getoriginalBm();

                Register rg = new Register();
                senderName = rg.getSenderName();

                com.androidapp.youjigom.FirebasePost post=
                        new com.androidapp.youjigom.FirebasePost
                                (StringImage, receiverName, receiverCountry, senderName);
                postValues=post.toMap();

                childUpdates.put("users/" + receiverName, postValues);
                databaseReference.updateChildren(childUpdates);
            }
        });
        </pre></code>
        
"예"버튼의 onClick 함수 안에 이미지 저장 코드를 작성합니다. 이미지 전송도 회원가입시 사용자 정보를 저장할 때처럼 FirebasePost 파일의 toMap 함수를 이용했습니다.<br><br>
이미지는 String으로 변환한 값이 CameraActivity에서 작성된 getoriginalBm 함수를 통해 넘어오게 됩니다.

<b>jiminjimin</b> 이라는 사용자로 로그인하고 <b>jjj</b>라는 사용자에게 사진을 보내면 데이터베이스에 다음과 같이 저장됨을 확인할 수 있습니다.<br>

<img src="https://user-images.githubusercontent.com/79952145/121300841-51a13800-c932-11eb-832b-cffec188e183.png" width="400"><br>
이미지는 받는 사람의 정보 안에 보내는 사람의 이름과 함께 추가로 저장됩니다.<br><br>

## 2-6 전송된 이미지 확인<br>
전송된 이미지를 확인하기 위해 imgList 자바파일과 xml파일을 만들어주고 xml파일에는 listView만 배치해줍니다.<br>

<pre><code>
ListView listView = findViewById(R.id.listView); //받은 사진 목록을 보여주는 listView 입니다.
ArrayList<String> items = new ArrayList<>(); //사진을 보낸 사람의 이름을 저장할 items라는 ArrayList를 만들어줍니다.
adapter = new CustomAdapter(this, 0, items);

fDatabase = FirebaseDatabase.getInstance();
DatabaseReference reference = fDatabase.getReference();
</pre></code>

필요한 변수를 선언해준 후, 이미지가 저장될 경로에 이벤트리스너를 달아줍니다.<br>

<pre><code>
reference.child("users/jjj").addValueEventListener(new ValueEventListener() {
            //지정된 경로에 이미지가 저장되면 이벤트리스너가 실행됩니다.
            @Override
            public void onDataChange(@NonNull DataSnapshot snapshot) {
                for (DataSnapshot dataSnapshot : snapshot.getChildren()) {
                    if (dataSnapshot.getKey().equals("senderName")){
                        //로그인한 사용자의 이름을 뽑아 user 변수에 저장 후, items에 추가해줍니다.
                        user = dataSnapshot.getValue().toString();
                        items.add(user);
                        Log.d("TAG","items: "+user);
                        //listView에 adapter를 연결해줍니다.
                        listView.setAdapter(adapter);
                    }
                }
            }
</pre></code>

이미지가 저장되면 이벤트리스너 안에 코드가 실행되면서 senderName 필드에 저장된 값이 user에 저장되고 그 값을 items 배열에 추가해줍니다.<br><br>
그 후 listView에 adapter를 연결해주면 리스트뷰에 로그인한 사용자가 받은 사진 목록이 뜨게 됩니다.<br>

<pre><code>
public class CustomAdapter extends ArrayAdapter<String> {
        private ArrayList<String> items;

        public CustomAdapter(Context context, int textViewResourceId, ArrayList<String> objects){
            super(context, textViewResourceId, objects);
            this.items = objects;
        }

        public View getView(int position, View convertView, ViewGroup parent){
            View v = convertView;
            if (v == null){
                LayoutInflater vi = (LayoutInflater)getSystemService(Context.LAYOUT_INFLATER_SERVICE);
                v = vi.inflate(R.layout.item, null);
            }

            TextView txtName = (TextView)v.findViewById(R.id.txtName);

            if (user.equals(items.get(position))) {
                txtName.setText(items.get(position));
            }
            return v;
        }
    }
</pre></code>

adapter는 CusteomAdapter함수를 따로 만들어서 사용해야합니다.<br><br>
리스트뷰에 목록을 띄워줄때 사용할 item.xml파일을 하나 더 작성해주고 getView 함수에서 item.xml파일과 adapter를 연결해주면 이미지 목록이 성공적으로 뜹니다.

<img src="https://user-images.githubusercontent.com/79952145/121304250-12c1b100-c937-11eb-80ab-fba600f7ddad.png" width="400"><br>

리스트뷰를 클릭하면 보낸 사람의 이름과 사진을 보여주는 image.xml파일을 추가로 작성해줍니다.<br><br>
image.xml 파일에는 사진을 불러올 imageView와 보내는 사람의 이름을 표시해줄 TextView만 배치해줍니다.<br>

<pre><code>
//listView를 클릭하면 일어나는 이벤트 처리입니다.
        listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> adapterView, View view, int position, long l) {
                setContentView(R.layout.image);

                TextView txtNameGet = findViewById(R.id.txtNameGet);
                ImageView imgGet = findViewById(R.id.imgGet);
</pre></code>

listView의 클릭 이벤트리스너에서 TextView와 ImageView를 선언해줍니다.<br>

<pre><code>
              reference.child("users/jjj").addValueEventListener(new ValueEventListener() {
                    @Override
                    public void onDataChange(@NonNull DataSnapshot snapshot) {
                        for (DataSnapshot dataSnapshot : snapshot.getChildren()) {
                            if (dataSnapshot.getKey().equals("image")){
                                //스트링 값으로 저장된 이미지를 가져와 image변수에 저장합니다.
                                image = dataSnapshot.getValue().toString();

                                byte[] b = Base64.decode(image, Base64.DEFAULT);

                                bitmap = BitmapFactory.decodeByteArray(b, 0, b.length);
                                Log.d("TAG","bitmap: "+bitmap);
                                //image변수에 저장된 스트링 값을 바이트 배열로 바꾸고 비트맵으로 변환하여 이미지뷰에 띄워줍니다.
                                imgGet.setImageBitmap(bitmap);
                            }
                        }
                    }
                    
                    //받는 사람이름을 텍스트뷰에 띄워줍니다.
                    txtNameGet.setText(user);
</pre></code>

지정된 경로에서 image 필드 안에 저장된 이미지의 스트링 값을 image 변수에 저장한 후 그것을 byte배열로 바꾸고 bitmap으로 바꾼 후, Imageview에 띄워줍니다.<br><br>
TextView에는 위에서 user 변수안에 저장해두었던 보낸 사람 이름을 띄워줍니다.<br><br>
확인하면 다음과 같이 보낸 사람과 이미지를 잘 띄워주는 것을 확인할 수 있습니다.

<img src="https://user-images.githubusercontent.com/79952145/121306240-8cf33500-c939-11eb-9888-f3a0efa9d6b8.png" height="200"><br>

## 2-7 환경설정 - 윤효묵<br>
### (1) 소개<br>
환경설정은 언어 설정, 소리 설정, 알림 설정의 3가지 버튼으로 이루어져 있으며, 각각의 버튼 클릭시 핸드폰에 내재되어있는 시스템 설정으로 들어가게 해줍니다. 시스템 설정에서 언어, 소리, 알림 기능을 수정할 수 있습니다.<br>
### (2) 환경설정 구성<br>
+ SettingActivity.java, activity_setting.xml을 만듭니다. activity_setting.xml 파일에 환경설정 화면과 맞는 코드를 알맞게 입력합니다.<br>
+ SettingActivity.java 파일에 다음과 같이 3가지 버튼을 인식시키고, activity_setting.xml과 연결합니다.
<pre><code>
public class Setting extends AppCompatActivity {

    private Button buttonSetting;
    private Button buttonSetting2;
    private Button buttonSetting3;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_setting);
        buttonSetting = (Button) findViewById(R.id.setting_btn);
        buttonSetting2 = (Button) findViewById(R.id.setting2_btn);
        buttonSetting3 = (Button) findViewById(R.id.setting3_btn);
</pre></code>

#### Intent
+ intent를 이용해서 각각의 버튼을 클릭했을 때, 시스템 설정으로 이동할 수 있게 코드를 입력합니다.
+ 소리 설정
<pre><code>
buttonSetting.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(android.provider.Settings.ACTION_LOCALE_SETTINGS);   // ACTION_LOCALE_SETTINGS은 시스템 설정에서 언어 설정을 뜻합니다.
                startActivity(intent);
            }
        });
</pre></code>

+ 언어 설정
<pre><code>
 buttonSetting2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(android.provider.Settings.ACTION_SOUND_SETTINGS);   // ACTION_SOUND_SETTINGS은 시스템 설정에서 소리 설정을 뜻합니다.
                startActivity(intent);
            }
        });
</pre></code>

+ 알림 설정
<pre><code>
buttonSetting3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(android.provider.Settings.ACTION_NOTIFICATION_LISTENER_SETTINGS);   // ACTION_NOTIFICATION_LISTENER_SETTINGS은 시스템 설정에서 알림 설정을 뜻합니다.
                startActivity(intent);
            }
        });
</pre></code>

# 3. 동작영상

#### ppt와 구동 화면을 이용해서 좀 더 쉽게 이해할 수 있는 동작영상을 만들었습니다.
(동작영상 : https://www.youtube.com/watch?v=i3PL5pLVu38)
