# ViewStub

    <androidx.appcompat.widget.ViewStubCompat
        android:id="@+id/uiStub"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:animateLayoutChanges="true"
        android:inflatedId="@+id/uiStub"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="parent" />

        inflateLayout(R.layout.firtView, this, "tag1")

          @SuppressLint("RestrictedApi")
         fun inflateLayout(@LayoutRes res: Int, listener: ViewStubCompat.OnInflateListener?, tag: String) {

        if (listener != null) {
            binding.uiStub.setOnInflateListener(listener)
        }
        binding.uiStub.layoutResource = res
        
         binding.uiStub.tag = tag
        binding.uiStub.inflate()
       }
       
       class MainActivity , ViewStubCompat.OnInflateListener {


             override fun onInflate(stub: ViewStubCompat, inflated: View) {

        when (inflated.tag) {
            FIRST_SCREEN -> { 
                updateFirstScreenView(inflated)
            }
       
        }//CHECK FOR TAG
        }

       }
