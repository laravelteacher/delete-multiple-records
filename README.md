# delete-multiple-records

                                 
								 How to delete multiple records using Laravel Eloquent
								 
								 
I want to be able to delete multiple records from the database. I have the id's of all the records I wish to delete.

I have a Group Chat and i send message for all Subscribers


I have a Table to name Message and i want to Delete multi records in that, so i have to say to Function Delete that Records are this Id


first Example is the below code

$messages =  Message::where(['group_id' => $id])->first();  // remove all messages from this Group
        foreach($messages as $value) {
            message::where(['group_id' => $id])->delete(); 
        }

2. or use this code

Message::whereIn('group_id',explode(",",$id))->delete();

3. 

//delete a groupe and remove all Subscribes
    public function deleteGroup($id)
    {
        
        message::where('group_id' , $id)->delete(); 

        return redirect('/home')->with('success', 'Group has been deleted');
    }

Thanks 		
